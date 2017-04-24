#!/usr/bin/env bash

swapsize=2048

grep -q "swapfile" /etc/fstab

if [ $? -ne 0 ]; then
	echo 'swapfile not found. Adding swapfile.'
	fallocate -l ${swapsize}M /swapfile
	chmod 600 /swapfile
	mkswap /swapfile
	swapon /swapfile
	echo '/swapfile none swap defaults 0 0' >> /etc/fstab
else
	echo 'swapfile found. No changes made.'
fi

apt-get update && apt-get install -y docker.io make

git clone https://github.com/getsentry/onpremise.git
cd onpremise/
echo "mail.username: 'email'" >> config.yml
echo "mail.password: ''" >> config.yml
echo "mail.use-tls: true" >> config.yml
echo "mail.host: 'smtp.gmail.com'" >> config.yml
echo "mail.port: 587" >> config.yml
make build

docker run \
  --detach \
  --name sentry-redis \
  redis:3.2-alpine

docker run \
  --detach \
  --name sentry-postgres \
  --env POSTGRES_PASSWORD=secret \
  --env POSTGRES_USER=sentry \
  postgres:9.5

docker run \
  --detach \
  --name sentry-smtp \
  tianon/exim4


docker run --rm sentry-onpremise config generate-secret-key > key
SENTRY_SECRET_KEY=$(cat key)

docker run \
  --rm \
  -it \
  --link sentry-redis:redis \
  --link sentry-postgres:postgres \
  --link sentry-smtp:smtp \
  --env SENTRY_SECRET_KEY=${SENTRY_SECRET_KEY} \
  sentry-onpremise \
  upgrade

docker run \
  --detach \
  --link sentry-redis:redis \
  --link sentry-postgres:postgres \
  --link sentry-smtp:smtp \
  --env SENTRY_SECRET_KEY=${SENTRY_SECRET_KEY} \
  --name sentry-web \
  --publish 9000:9000 \
  sentry-onpremise \
  run web

docker run \
  --detach \
  --link sentry-redis:redis \
  --link sentry-postgres:postgres \
  --link sentry-smtp:smtp \
  --env SENTRY_SECRET_KEY=${SENTRY_SECRET_KEY} \
  --name sentry-worker \
  sentry-onpremise \
  run worker

docker run \
  --detach \
  --link sentry-redis:redis \
  --link sentry-postgres:postgres \
  --link sentry-smtp:smtp \
  --env SENTRY_SECRET_KEY=${SENTRY_SECRET_KEY} \
  --name sentry-cron \
  sentry-onpremise \
  run cron
