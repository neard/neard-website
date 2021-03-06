* Start Neard.
* Switch to the {{ page.module.label }} version you have extracted on Neard :

![](/img/modules/{{ page.module.name }}/switch-version.png)

{% include callout.html type="primary" text="If you have the [warning icon](/doc/faq/#warning-icon-in-apache--php-versions-menu-) on your PHP version, **you will have to switch the Apache version first**." %}

## OpenSSL

| PHP version            | OpenSSL version |
| ---------------------- | --------------- |
| **5.2.17**             | 0.9.8           |
| **5.3.x**              | 0.9.8           |
| **5.4.x**              | 0.9.8           |
| **5.5.x**              | 1.0.1           |
| **5.6.0** > **5.6.26** | 1.0.1           |
| **5.6.28** > **5.6.x** | 1.0.2           |
| **7.0.x**              | 1.0.2           |
| **7.1.x**              | 1.0.2           |
| **7.2.x**              | 1.1.0           |
| **7.3.x**              | 1.1.0           |
| **7.4.x**              | 1.1.1           |
| **8.0.0**              | 1.1.1           |

## Additionnal extensions

|                                                           | PHP 5.2.x                   | PHP 5.3.x                   | PHP 5.4.x                   | PHP 5.5.x                   | PHP 5.6.x                   | PHP 7.0.x                   | PHP 7.1.x                   | PHP 7.2.x                   | PHP 7.3.x                   | PHP 7.4.x                   | PHP 8.0.x                   |
| --------------------------------------------------------- |:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
| **[php_apc](https://pecl.php.net/package/APC)**           | {% include icon-nok.html %} | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} |
| **[php_imagick](https://pecl.php.net/package/imagick)**   | {% include icon-nok.html %} | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-nok.html %} |
| **[php_memcache](https://pecl.php.net/package/memcache)** | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **[php_mongo](https://pecl.php.net/package/mongo)**       | {% include icon-nok.html %} | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} |
| **[php_mongodb](https://pecl.php.net/package/mongodb)**   | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-nok.html %} |
| **[php_ssh2](https://pecl.php.net/package/ssh2)**         | {% include icon-nok.html %} | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-nok.html %} |
| **[php_vld](https://pecl.php.net/package/vld)**           | {% include icon-nok.html %} | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-nok.html %} | {% include icon-nok.html %} |

## PEAR

PEAR is integrated in each PHP module through the `install-pear-nozlib.phar` standalone installer.

| PEAR version | PHP 5.2.x                   | PHP 5.3.x                   | PHP 5.4+                    |
| ------------ |:---------------------------:|:---------------------------:|:---------------------------:|
| **1.7.2**    | {% include icon-ok.html %}  | {% include icon-nok.html %} | {% include icon-nok.html %} |
| **1.9.5**    | {% include icon-nok.html %} | {% include icon-ok.html %}  | {% include icon-nok.html %} |
| **1.10.1**   | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-ok.html %}  |
| **1.10.5**   | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-ok.html %}  |

## Apache compatibility table

|               | Apache 2.2.x                | Apache 2.4.x                |
| ------------- |:---------------------------:|:---------------------------:|
| **PHP 5.2.x** | {% include icon-ok.html %}  | {% include icon-nok.html %} |
| **PHP 5.3.x** | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **PHP 5.4.x** | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **PHP 5.5.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  |
| **PHP 5.6.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  |
| **PHP 7.0.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  |
| **PHP 7.1.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  |
| **PHP 7.2.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  |
| **PHP 7.3.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  |
| **PHP 7.4.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  |
| **PHP 8.0.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  |

## MongoDB compatibility table

PHP 5.3 and 5.4 includes the old [php_mongo](https://pecl.php.net/package/mongo) extension that is not compatible with MongoDB 3.2+.<br />
More infos : [https://docs.mongodb.com/ecosystem/drivers/php](https://docs.mongodb.com/ecosystem/drivers/php)

|               | MongoDB 2.6                 | MongoDB 3.0                 | MongoDB 3.2+                |
| ------------- |:---------------------------:|:---------------------------:|:---------------------------:|
| **PHP 5.2.x** | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} |
| **PHP 5.3.x** | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-nok.html %} |
| **PHP 5.4.x** | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-nok.html %} |
| **PHP 5.5.x** | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **PHP 5.6.x** | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **PHP 7.0.x** | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **PHP 7.1.x** | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **PHP 7.2.x** | {% include icon-ok.html %}  | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **PHP 7.3.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **PHP 7.4.x** | {% include icon-nok.html %} | {% include icon-ok.html %}  | {% include icon-ok.html %}  |
| **PHP 8.0.x** | {% include icon-nok.html %} | {% include icon-nok.html %} | {% include icon-nok.html %} |

## ImageMagick and Imagick extension

| Imagick version            | ImageMagick library         |
| -------------------------- |:---------------------------:|
| **3.3.0**                  | 6.8.9-1 Q16 x86 2014-05-08  |
| **3.4.3RC1**               | 6.8.9-1 Q16 x86 2014-05-08  |
| **3.4.3**                  | 6.9.3-7 Q16 x86 2016-03-27  |
| **3.4.3** (PHP 7.2, 7.3)   | 7.0.7-11 Q16 x86 2017-11-23 |
| **3.4.4** (PHP 7.4)        | 7.0.7-11 Q16 x86 2017-11-23 |
