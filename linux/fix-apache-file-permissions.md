You’ll need to fire up terminal, ssh to the server, and then execute these commands:

> cd /var/www
sudo chmod 775 html
sudo chgrp www-data html
sudo chmod g+s html

+s makes permissions sticky so that all files will inherit from the parent directory. This was the setting I was missing.

Open up /etc/ssh/sshd_config. I use nano so:


>sudo nano /etc/ssh/sshd_config

Hit CTRL+W and look for “subsystem” which is typically located near the bottom of the file. Change

> subsystem sftp /usr/lib/openssh/sftp-server

to 

> subsystem sftp /usr/lib/openssh/sftp-server -u 0002

If you already have files in the html folder, you’ll want to run these commands to reset the permissions:

> cd /var/www/
sudo chgrp -R www-data
find . -type f -exec chmod 664 {} \;
find . -type d -exec chmod 775 {} \;
