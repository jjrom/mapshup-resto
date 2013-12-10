mapshup-resto
=============

Dedicated build of mapshup for the RESTo framework (http://github.com/jjrom/resto)

Installation
============

This document supposes that mapshup-resto application will be installed in $TARGET directory

Apache configuration (Linux ubuntu)
--------------------------------------

1. Add the following rule to /etc/apache2/sites-available/default file

        Alias /mapshupresto/ "/$TARGET/"
        <Directory "/$TARGET/">
            Options -Indexes -FollowSymLinks
            AllowOverride None
            Order allow,deny
            Allow from all
        </Directory>

Note: $TARGET should be replaced by the $TARGET value (i.e. if $TARGET=/var/www/mapshupresto, then put /var/www/mapshupresto in the apache configuration file)

2. Relaunch Apache

        sudo apachectl restart

Build mapshup-resto
-------------------

The first time, you need to peform a complete build

        ./build.sh -a -t $TARGET

Once mapshup is cloned and compiled, you need to perform a partial build each time you change a file from the src directory.

        ./build.sh -t $TARGET
