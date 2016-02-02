# stats-1.0.3-patch
[PECL stats package](http://php.net/manual/en/book.stats.php) for PHP5 with patch for [Bug #57830](https://bugs.php.net/patch-display.php?bug_id=57830&patch=fix_randlib.c_add_static&revision=latest)

[original source](http://pecl.php.net/package/stats)

[installation tutorial](http://www.sitepoint.com/install-php-extensions-source/)

1. install dependencies
  - Ubuntu # apt-get install php5-dev php5-mysql gcc libpcre3-dev build-essential php-pear
  - RHEL # yum install php-devel php-mysql gcc libtool php-pear
2. # pecl install package.xml
3. add "extension=stats.so" to php.ini
4. restart web server

##Why?
the current PECL installer requires PHP7, so this provides a manual way to install the stats functions on servers running PHP5
###INITGN called before random number generator initialized -- abort!
if you are seeing this error message in the apache logs when using the random generator functions like `stats_rand_gen_normal()` and the browser is only showing something like `No data received` then that is because of [Bug #57830](https://bugs.php.net/patch-display.php?bug_id=57830&patch=fix_randlib.c_add_static&revision=latest) and this patched version is for you.
