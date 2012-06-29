# PostgreSQL Module Module

## Maintainer Contact

 * Sam Minnee (Nickname: sminnee) <sam@silverstripe.com>

## Requirements

* SilverStripe 2.4
* PostgreSQL 8.3.x or greater must be installed
* PostgreSQL <8.3.0 may work if T-Search is manually installed
*  Known to work on OS X Leopard, Windows Server 2008 R2 and Linux

## Documentation

Move the 'postgresql' folder to the root level of the project. You'll need to 
create a database with the desired name manually. 

Run dev/build and you should be set.

## Usage Overview

See docs/en for more information about configuring the module.
	
## Known issues

All column and table names must be double-quoted.  PostgreSQL automatically 
lower-cases columns, and your queries will fail if you don't.

Ts_vector columns are not automatically detected by the built-in search 
filters.  That means if you're doing a search through the CMS on a ModelAdmin
object, it will use LIKE queries which are very slow.  If you're writing your 
own front-end search system, you can specify the columns to use for search 
purposes, and you get the full benefits of T-Search.

If you are using unsupported modules, there may be instances of MySQL-specific 
SQL queries which will need to be made database-agnostic where possible.