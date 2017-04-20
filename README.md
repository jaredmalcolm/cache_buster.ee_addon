# Cache Buster

An ExpressionEngine plugin that adds a simple cache buster to your flat file references. This is a forked project to make the plugin compatible with EE3


## Compatibility

* ExpressionEngine 3.x

*For ExpressionEngine 1.6x & 2.x see the original project [https://github.com/erikreagan/er.cache_buster.ee_addon](https://github.com/erikreagan/er.cache_buster.ee_addon)*

## Installation

* *ExpressionEngine 3.x:* Upload the <code>/system/user/addons/cache_buster</code> directory to the <code>/system/user/addons/cache_buster</code> directory.


## Purpose

Using ExpressionEngine's CSS template provides a nice cache buster string of the most recent time
the template was saved to the database. This is quite handy but still requires EE to process the template.

This plugin will take a file path and use PHP to check the modification time returning a cache busting
string like ExpressionEngine's. This allows you to server flat files from your server without having
ExpressionEngine's template parser run through the code first. It is very simple to use.


## Usage

There are 3 parameters. One is required and the other two are optional.

`{exp:cache_buster file="/css/style.css"}`

This will return

`/css/style.css?v=1266264101`

Where "1266264101" is the UNIX timestamp of the last time /css/style.css was saved to the server.

You can change the separator between the file and the timestamp with the use of separator="" in the tag.

`{exp:cache_buster file="/css/style.css" separator="?"}`

This will return

`/css/style.css?1266264101`

*Server Root*

If your file isn't being read by the plugin then the server root might not be the right path. The plugin assumes that your file will reside on your server's DOCUMENT_ROOT variable. If this is not accurate you can manually define the root with the root_path parameter. *Do not include a trailing slash.*

`{exp:cache_buster file="/css/style.css" root_path="/home/mysite/subdirectory/templates"}`


## Change Log

*Apr 20th, 2017: 2.0.0*

* Converted to EE3 plugin

*Feb 17th, 2011: 1.1.1*

* Bug: Fixed bug where root_path wasn't set correctly

*Mar 27th, 2010: 1.1.0*

* Feature: added root_path parameter for manually entering server root
* Feature: EE2.x compatibility added

*Mar 27th, 2010: 1.0.1*

* Assigned license to add-on: "Creative Commons Attribution-No Derivative Works 3.0 Unported":http://creativecommons.org/licenses/by-nd/3.0/

*Feb 15th, 2010: 1.0.0*

* Initial Release