---
layout: md
title: Install
---
<h1 class="page-header">Install</h1>

## Requirements

* PHP 5.3.3 or later
    * MySQL PDO extension
    * GD extension (recommended)
* MySQL 5 Server
* Web server with support for URL rewrites
    * Apache .htaccess file and nginx sample configuration included
    * Lighttpd and IIS 7+ should work, but will require custom configuration


## Installation

The installation process for Phproject should be reasonably simple compared with Redmine or other project management systems.

1. Download the [latest stable release](https://github.com/Alanaktion/phproject/zipball/release) or clone the git repository and optionally checkout the release branch
2. Extract the zip archive to a web-accessible directory with write access
3. Create a database on your MySQL server
4. Navigate to the application and complete the installation

## Additional Setup
Additional configuation options not available from the installer can be found in `config-base.ini`. These options can be copied to `config.ini` and edited. You should avoid changing the `config-base.ini` file to make updating easier.

To see performance information and additional details about errors, change `DEBUG` in `config.ini`. This option supports levels 0-3, with 3 being the most verbose.
<span class="text-danger">You should always use 0 in a production environment!</span>

Phproject is designed to be fast, but you can still increase performance by installing an opcode caching layer like APC. Using APC also greatly increases the speed of temporary cached data, including minified code and heavy, cacheable database queries.


## Updating
Simply pulling the repo again will usually work for updates. If `database.sql` has been modified, you will need to manually merge the changes into your database. If something breaks after updating, clearing the APC cache or the `tmp/` and `tmp/cache/` directories of everything except `.gitignore` will usually solve the problem.