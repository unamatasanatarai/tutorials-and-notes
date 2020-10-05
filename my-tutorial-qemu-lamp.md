## Setup QEMU

1. download linux alpine
1. set it up by running qmanager https://gist.github.com/unamatasanatarai/c72a687ef9806481697bc9c0a3e768ea

## Allow ssh
vi /etc/ssh/sshd_config
PermitRootLogin yes

## Enable community repositories
1. vi /etc/apk/repositories
1. uncomment the line with "community"
1. apk update && apk upgrade

## Setup mariadb

1. apk add mariadb mariadb-client
1. /etc/init.d/mariadb setup # (this takes forever to complete)
1. in /etc/my.cnf.d/mariadb-server.cnf uncomment "bind-address=0.0.0.0"
1. in /etc/my.cnf.d/mariadb-server.cnf comment "# skip-networking"
1. rc-update add mariadb
1. mariadb-secure-installation
1. rc-service mariadb restart

Log into mariadb
create user 'toor'@'%' identified by 'pass';
grant all privileges on *.* to 'toor'@'%' with grant option;
flush privileges

## Setup apache
1. apk add apache2
1. rc-update add apache2
1. rc-service apache2 start

## Setup php
1. apk add php7 php7-apache php7-mysqli php7-json php7-simplexml php7-curl php7-dom
1. rc-service apache2 restart

## Some more tools?
1. apk add vim htop fzf
1. apk add nodejs yarn
1. apk add git
