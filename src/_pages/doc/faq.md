---
title: FAQ
permalink: /doc/faq/
sidebar: doc
---
{% include vars.html %}

## Where is the source code of neard.exe ?

`neard.exe` is based on [Aestan Tray Menu 1.6.2](http://obroekma.home.xs4all.nl/aetraymenu/){:target="_blank"}.<br />
You can download the source code here : [aetraymenu_src.zip](http://obroekma.home.xs4all.nl/aetraymenu/aetraymenu_src.zip){:target="_blank"}<br />
Neard uses the exe and the ini file to generate the tray menu.

## How to upgrade from a previous release ?

Neard is a portable application and does not provide a setup at this time.<br />
To upgrade from a previous release, you have to follow the instructions in the [UPGRADE.md]({{ var_repo_url }}/blob/master/UPGRADE.md){:target="_blank"} file.

## Why Neard icon in the system tray is yellow or red ?

Neard icon has 3 states :

* ![](/img/faq/neard-icon-green.png) : All enabled services are started
* ![](/img/faq/neard-icon-yellow.png) : One or more enabled services are stopped
* ![](/img/faq/neard-icon-red.png) : All enabled services are stopped

To check from the Services Manager, click Start > Run and type `services.msc` and check the status of Neard* services :

![](/img/faq/windows-services.png)

## Warning icon in Apache / PHP versions menu ?

![](/img/faq/warning-icon-switch-version.png)

![](/img/faq/apache-not-compatible-php.png)

> Apache 2.4.20 does not seem to be compatible with PHP 5.2.17

The error message explains himself why you have a warning icon when you want to switch version.<br />
Please read [Apache compatibility table page](/bins/apache/#compatibility-table).

## What is the default password for root user on MySQL / MariaDB ?

By default, there is no password for root user.

## How to use MySQL and MariaDB simultaneously with PHP ?

By default MySQL is started on port 3306 and MariaDB on port 3307.<br />
Here is an example using PDO to access a database named `wordpress` installed on MySQL and MariaDB :

```php?start_inline=1
$mysql = new PDO('mysql:host=127.0.0.1;port=3306;dbname=wordpress', 'root', '');
$mysqlStmt = $mysql->query("SELECT * FROM wp_comments");
var_dump($mysqlStmt->fetchAll(PDO::FETCH_ASSOC));

$mariadb = new PDO('mysql:host=127.0.0.1;port=3307;dbname=wordpress', 'root', '');
$mariadbStmt = $mariadb->query("SELECT * FROM wp_comments");
var_dump($mariadbStmt->fetchAll(PDO::FETCH_ASSOC));
```


## What is the default user / password on PostgreSQL ?

The user is **postgres** and there is no password for this user.

## PostgreSQL start gives FATAL: role does not exist

When PostgreSQL is started as a service, you can have this error :

```text
LOG:  database system was shut down at 2013-06-13 00:54:33 UTC
LOG:  autovacuum launcher started
LOG:  database system is ready to accept connections
FATAL:  role "John" does not exist
 done
server started
```

This happens when you run pg_ctl start with the -w (wait) option like Neard, because it will try a test connection with a user that does not exist (in your case).<br />
But that's not really a problem (except for the confusing error message), because that proves that the server is up.

## What is the default user / password for FileZilla Server ?

The user is **root** and there is no password for this user.

## What is the default admin port for FileZilla Server ?

14147

## How to disable some services to launch on startup ?

There are two ways to disable some services to launch on startup.

First you can edit the `neard.conf` file and change the value to `0` for keys ending with `enable = "1"` below `BINS`.<br />
Example: `filezillaEnable = "0"`

Or you can go to the Neard menu.<br />
Example: **Neard tray menu > FileZilla > Enable / Disable**

![](/img/faq/bin-enable.png)

## A service will not start and does not display error via the menu

Aestan Tray Menu built in service manager is not handled by Neard in the Service menu :

![](/img/faq/not-start-no-error.png)

You can take look to the Windows Event Log to find out where the error occurred or use the Debug menu of the service (like Apache, MySQL or MariaDB).

## GitList - No repositories

When you go to [GitList](http://localhost/gitlist/){:target="_blank"} you probably get this message :

> Please, edit the config file and provide your repositories directory

By default Neard seek repositories in :
* `www` directory
* `C:\gitRepos`

If you have others folders to scan for repositories, you have to edit the file `tools\git\gitx.x.x\repos.dat` then refresh repositories :

![](/img/faq/git-refresh.png)

## WebSVN - No repositories

When you go to [WebSVN](http://localhost/websvn/){:target="_blank"} you probably get this message :

> Please set up a repository in include/config.php using $config->parentPath or $config->addRepository. See the installation guide for more details.

By default Neard seek repositories in your SVN binary folder.<br />
Example : `C:\neard\bin\svn\svn1.7.19\repos`

## Could not execute menu item (internal error)

![](/img/faq/aestan-could-not-execute.png)

> Could not execute menu item (internal error)<br />
> [EAccessViolation] Access violation at address XXXXXXXX in module 'neard.exe'. Read of address XXXXXXXX

Neard tray icon is based on [Aestan Tray Menu](https://obroekma.home.xs4all.nl/aetraymenu/){:target="_blank"}.<br />

There are several cases to reproduce this error :

* Execute multiple actions at the same time.
* Do not wait for an action ends.
* A procedure error with Neard based on `neard.ini` file.

For the last case you will have to [create an issue]({{ var_repo_url }}/issues/new){:target="_blank"}.

## http.exe missing MSVCR100.dll

![](/img/faq/http-msvcr100-dll.png)

> The program can't start because MSVCR100.dll is missing from your computer. Try reinstalling the program to fix this problem.

This error occurs because you probably have not installed the latests [Neard Visual C++ Redistributables Package]({{ site.github.baseurl }}/crazy-max/neard-misc#visual-c-redistributables-package){:target="_blank"}.

## Apache error 41d

![](/img/faq/apache-error-41d.png)

> Apache x.x.x (neardapache) service cannot be installed :<br />
> \- Cannot start the service : Error 41d (1053 : )<br />
> \- Conf errors detected :

See [http.exe missing MSVCR100.dll](#httpexe-missing-msvcr100dll)

## Apache status 1

![](/img/faq/apache-status-1.png)

> Apache x.x.x (neardapache) service cannot be installed :<br />
> \- Cannot start the service : Status 1 (1 : The service is not running)<br />

This problem could appear on Windows XP on the first launch of Neard.<br />
In this case, you must restart your computer.

## Unable to load dynamic library php_imagick.dll

![](/img/faq/unable-to-load-php-imagick.png)

> PHP Startup: Unable to load the dynamic library php_imagick.dll

See [http.exe missing MSVCR100.dll](#httpexe-missing-msvcr100dll)

## Neard has encountered a problem

![](/img/faq/neard-has-encountered-a-problem.png)

> Neard has encountered a problem and needs to close. We are sorry for the inconvenience.

This problem could appear on Windows XP.<br />
You have to install the latests [Neard Visual C++ Redistributables Package]({{ site.github.baseurl }}/crazy-max/neard-misc#visual-c-redistributables-package){:target="_blank"}.

## FileZilla Server.exe is not a valid Win32 application

![](/img/faq/filezilla-server-not-valid-win32.png)

> FileZilla Server.exe is not a valid Win32 application.

This problem could appear on Windows XP.<br />
Filezilla drops Windows XP support since 0.9.43 version.<br />
You have to download the 0.9.42 version. See [Filezilla page](/bins/filezilla).

## php.exe - Entry point not found

![](/img/faq/php-releasesrwlockexclusive-kernel32.png)

> The procedure entry point ReleaseSRWLockExclusive could not be located in the dynamic link library KERNEL32.dll

Most often reason to happen such error is you trying to set not tread safe extension in your PHP installation.<br />
On Neard **PHP is installed as Thread Safe**.