# Readme

## Install

* Clone your project `git clone https://github.com/sample.git`
* Run composer `composer install`
* Create & Import your database

**Command with mysql: `mysql -u[username] -p[password] -h[db_host] [db_name] < [file.sql]`**
* Run robo `./vendor/bin/robo install`
* In ./config directory, copy local-sample.php to local.php
* Don't forget to import your media directory
* Check grants in
  * ./logs/
  * ./security/
  * Media directory


## Architecture overview
* Add all grants to acf-json directory, in your theme root
* To add a Wordpress Plugin, run `composer require "wpackagist-plugin/[plugin-slug]": "[plugin-version]"`

**Find your dependencie in [wpackagist](https://wpackagist.org/)**
* Config required :
  * application.php : config your path and general constants
  * local.php       : local configuration (will be ignore in deploy task and git)
  * salt-keys.php   : WP salt keys ([generate](https://api.wordpress.org/secret-key/1.1/salt/))
  * vars.php        : Project vars
  * environments/   : Your environments settings
  * htaccess/       : Htaccess rules. Will be minify in build task. You can override a part by environment (sample: htacess-[part]-[environment]
