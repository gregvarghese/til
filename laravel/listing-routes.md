
$ php artisan routes
You will then see all of your routes, nicely displayed on your console.

Here's a partial list of routes running the laravel-recipes site (edited to fit on small screens).

+---------------------------+-------------------------+----------------+
| URI                       | Action                  | Before Filters |
+---------------------------+-------------------------+----------------+
| GET /                     | PageController@home     | cache.get      |
| GET contents              | PageController@contents | cache.get      |
| GET faq                   | PageController@faq      | cache.get      |
| GET topics                | PageController@topics   | cache.get      |
| GET codes                 | PageController@codes    | cache.get      |
+---------------------------+-------------------------+----------------+

You can also filter the list.

To filter and only show the routes beginning with ho try this.

$ php artisan routes --name=ho
Or to filter the routes by path, you can use the --path= option.

$ php artisan routes --path=c
This will display all your routes with paths beginning the letter c.