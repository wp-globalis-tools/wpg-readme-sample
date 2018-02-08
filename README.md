# Readme

## Install

* Clone your project `git clone https://github.com/sample.git`
* Run composer `composer install`
* Create & Import your database

**Command with mysql: `mysql -u[username] -p[password] -h[db_host] [db_name] < [file.sql]`**
* Run robo install `./vendor/bin/robo install`
* In ./config directory, copy local-sample.php to local.php
* Don't forget to import your medias directory
* Check permissions on
  * ./logs/
  * ./security/
  * Medias directory


## Architecture overview
* We use ACF plugin with his json feature to synchronise custom fields. Please add write access to your acf-json directory, in your theme root
* To add a Wordpress Plugin, run `composer require "wpackagist-plugin/[plugin-slug]": "[plugin-version]"`
* Your web root path must be set to /web directory (vhost or web path in your robo properties)

**Find your dependencie in [wpackagist](https://wpackagist.org/)**
* Config (*./config/*) :
  * application.php : config yours paths and general constants
  * local.php       : local configuration (will be ignore in git and deploy task)
  * salt-keys.php   : WP salt keys ([generate](https://api.wordpress.org/secret-key/1.1/salt/))
  * vars.php        : project vars
  * environments/   : your environments settings
  * htaccess/       : htaccess rules. Will be minify in build task. You can override a part by environment (example: htacess-urls-[environment]
* Robo
  * We use robo tasks runner
  * Robo tasks are define in `./Robofile.php`

## Build
### Command usage
* htaccess : `./vendor/bin/robo build:htaccess`
* theme    : `./vendir/bin/robo build:theme [--skip-styles] [--skip-scripts] [--skip-images] [--skip-fonts]`
  
## Deploy
### Command usage
`./vendor/bin/robo deploy:[environment] [branch]`

## Project

## References
* [wp-cubi](https://github.com/globalis-ms/wp-cubi)
* [Wonolog](https://github.com/inpsyde/Wonolog)
* [wp-cli](https://wp-cli.org/)
* [Globalis-ms](https://www.globalis-ms.com/)
