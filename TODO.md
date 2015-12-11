
TODO
===

In the README

* README's #2 can be explicit about the mysql56 service in cloud.gov
* README's #4 should say "edit `htdocs/sites/...`"
* README's #4 should give guidance about generating a salt for n00bs (eg "md5 a random file")
* Advise a better strategy for storing the salt than in settings.php (eg user-provided service?)

In the buildpack options

* Figure out why the PHP APC/Opcache isn't working (optimization)

In .extensions/drupal/extension.py

* Document how to upgrade: 
    * change the Drupal version
    * generate a new SHA hash

In the manifest

* Document the memory needed for install vs post-install (128M was too little for install, but might be fine for normal ops)

In the settings.php

* Resolve "dbname" vs "name" for services parameter (hard-coded for now, should handle both)

In Drupal configuration

* Turn *off* automatic updates during install
* Show how to set up S3 usage [based on Pivotal's instructions](https://blog.pivotal.io/pivotal-cloud-foundry/products/how-to-deploy-drupal-to-pivotal-cf-within-seconds)
* What is needed for handling PHP sessions gracefully??

General improvements

* Have the buildpack use drush for configuring the site, in order to minimize modifications to the stock Drupal settings.php (see [ADDITIONAL_PREPROCESS_COMMANDS in the buildpack docs](https://docs.cloudfoundry.org/buildpacks/php/gsg-php-config.html); this can point to a script with drush commands included in the repository)
    * [Install drush](http://docs.drush.org/en/master/install/) (use Composer?)
    * [Drive the install with drush](http://drushcommands.com/drush-7x/site-install/site-install)
    * Have it install the USFWDS theme to show how to use drush for plugins, themes, etc
    * Advise in the README where to modify the set of drush commands to be run.
