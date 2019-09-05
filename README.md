# Nextcloud

A safe home for all your data. Access & share your files, calendars, contacts, mail & more from any device, on your terms.

# About this image

The purpose of this nextcloud config is to enable a simple nextcloud instance running with https enabled. Self-signed certs can be created or replace with real ones.

This compose is originally based on [indiehosters/nextcloud] and then modified for linux servers io (https://www.linuxserver.io/)

Please see https://hub.docker.com/r/linuxserver/nextcloud for more details on how to use this container.

## Set your variables
Set the db passwords

````bash
 PASS=$(cat /dev/urandom | tr -dc 'a-zA-Z0-9' | fold -w 32 | head -n 1)
 echo MYSQL_ROOT_PASSWORD=$PASS >> .env
 echo MYSQL_PASSWORD=$PASS >> .env
````

NOTE: change the mystrongpassword to whatever you wish

Modify the user id to be your user id, which can by found by doing:
````bash
 id username
 uid=1000(dockeruser) gid=100(dockergroup) groups=100(dockergroup)
````

## Start your containers
````bash
 docker-compose up -d
````

You can now access your instance on the port 443 of the IP of your machine.

## Installation

Once started, you'll arrive at the configuration wizard.
At the `Database Setup` step, please enter the following:

  -  database user: nextcloud
  -  database password: mystrongpassword
  -  database name: nextcloud
  -  database server: db

And leave the rest as default.

Then you can continue the installation with the admin user.
