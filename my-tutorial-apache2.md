# Install apache2 on macos

1. `brew install apache2`
1. set ServerName in /etc/apache2/httpd.conf to `localhost`
1. change DocumentRoot to where you want to hold your website
1. change <Directory... to `<Directory "same as document root">`
1. AllowOverride All
1. uncomment # Virtual hosts
1. `sudo /usr/sbin/apachectl restart`

and then add php support!
1. uncomment "LoadModule php7_module"
