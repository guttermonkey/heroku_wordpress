# Heroku on Wordpress
## Using Postgres shared DB (if I can get it to work)

This is a fairly easy to do project, just follow these directions:

* Download the Wordpress package from http://www.wordpress.org
* Download the PG4WP plugin from http://wordpress.org/extend/plugins/postgresql-for-wordpress/
* Rename wp-config-sample.php as wp-config.php
* Initialize & commit a git repository
    * git init
    * git add .
    * git commit -m "Initial commit"
* Create a new heroku app
	* heroku create --stack cedar
* Add the shared-database addon
    * heroku addons:add shared-database
* Retrieve the database information from heroku
    * heroku config --long
* Fill the values into wp-config.php
* Commit the new changes
	* git add .
	* git commit -m "Added PG support & filled in config"
* Push to Heroku
	* git push heroku master
* Initialize and configure your new WP application on Heroku
    * access /wp-admin/install.php on the new site from your browser

My working sample can be found at http://young-ocean-5621.herokuapp.com