=== Plugin Name ===
Contributors: akandels
Donate link: http://www.vulnero.com/
Tags: zf, zend, zend framework, integration, framework, routing, routes, library
Requires at least: 3.0.0
Tested up to: 3.3.1
Stable tag: 1.0.1

Transform WordPress into an object-oriented CMS by implementing a Zend Framework application that interfaces with its API.

== Description ==

Vulnero does more than just provide an include to the Zend Framework components. It bootstraps Zend functionality to the WordPress core and its popular plugins to provide rapid application development on top of the WordPress content management platform.

##Bootstrapping (Zend_Application)##
Vulnero bootstraps as a Zend_Application, setting up WordPress hooks to initialize things like database connections sharing the WordPress configuration.

##Routing Requests##
The plugin hooks into and supersedes WordPress.s routing. Simply install a Zend_Router_Route_* compatible router to your routes.ini file and you can nab pages WordPress would normally handle and route them into your application.s controllers and view scripts.

##View Scripts##
When rendering your views, you have the option to specify your own layout or use WordPress to wrap your content. By using WordPress as a layout, you maintain the look and feel of your WordPress theme and even your widgets, sidebars and menus.

##Configuration (Zend_Config)##
Your application configuration is loaded and merged with WordPress' internal configuration for quick and easy access via a convenient Zend_Config object.

##Caching##
A Zend_Cache_Adapter can be specified or automatically detected with popular front and back-ends like Apc or Memcached. By default, it is used to cache much of bootstrapping, such as parsing your config.ini file and much of the WordPress integration to keep your application.

##Database##
A MySQL Zend_Db adapter using WordPress' configuration is bootstrapped allowing you to run queries against it directly using PDO or by creating Zend_Db_Table models.

##Authentication##
Zend_Auth_Adapters are bootstrapped against WordPress' user table automatically providing your application quick visibility into a user's login status and profile information. Users can be managed directly through WordPress' administration panel's users section. Access control lists can be setup using Zend_Acls to qualify access to different areas of your application.

== Installation ==

The easiest way to get up and running with Vulnero is to install the sample application. This includes a pre-configured Zend Framework application with submodules for Vulnero and the framework itself. Sample controllers, widgets, administration pages and configuration files are included to provide a solid foundation for you to build on.

##Installation##
1. Download the Vulnero sample application as a zip or clone the GitHub repository: git clone git://github.com/andrew-kandels/vulnero-app.git and upload it to your web server.
1. Copy the vulnero-app directory from step 1 into your WordPress installation's wp-content/plugins folder (you should rename it to your project's name, e.g. my-plugin).
1. Edit the wordpress-plugin.php file in the root directory and change the plugin name, url and author information at the top of the file. This is what will be displayed in WordPress.
1. Login to the WordPress administration panel by browsing to http://yourdomain.com/wp-admin.
1. Click the Settings link on the left side bar.
1. Click Permalinks in the expanded Settings area.
1. Make sure either Custom (with something like /%postname%/) or Post Name are selected and save changes.
1. Click Plugins on the left side bar.
1. Click the Activate link within the Vulnero section to activate the plugin.
1. Click on the Vulnero link on the left hand bar to configure your environment, cache and bootstrap resources (optional).

##Verifying##
The sample application includes a default helloworld route you can browse to to verify the plugin is installed and configured correctly: http://yourdomain.com/helloworld.

##Summary##
At this point, you have a fully functional Zend_Application up and running within your WordPress site.

== Frequently Asked Questions ==

= Where can find documentation and sample code? =

http://www.vulnero.com/

= What if I find a bug or want to contribute? =

Visit the project's GitHub page at https://www.github.com/andrew-kandels/vulnero

== Screenshots ==

== Changelog ==

= 1.0.1 =
* First project release, feature complete.

= 0.1.3 =
* Splitting off vulnero-app (the standalone plugin) as its own repository
* Various small bug fixes I've identified using the library for its first major project

= 0.1.2 =
* Refactored widgets slightly to simplify the capturing of options
* Another major routing overhaul, removed the concepts of layouts, using 100% WP page templates
* Renamed some files to better explain their purpose
* Unit tests and documentation updated to describe the latest functionality
* Moving caching, environment and bootstrap option configuration to the default admin page
* Added Zend Framework submodule to simplify installation if it's not in your include_path

= 0.1.1 =
* Major routing improvements and better use of the request and response objects
* Unit tests covering all present functionality in its entirety
* Move all Vulnero logic to library/Vulnero, separating from the Application
* New website with public source code serving as a sample application
* Online documentation
* API class separating WordPress API methods for better testability
* Better control over layouts and WordPress templates
* Simplifying installation

= 0.1.0 =
* First upload for the project.
* Includes the basic WordPress plugin structure and application folders.
* Extends WordPress routing with Zend application routing
* Bootstraps database, routing, config, layouts, views, database
* Controller view scripts display content within WordPress page templates as layouts
* Partial auth implementation
* Setup config and routes ini configuration files
* Setup default and error controllers
* Setup formatted exceptions
