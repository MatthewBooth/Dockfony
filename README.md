# Dockfony
Dockfony is a simple Symfony 4+ Docker Compose starter repository for all your Docker and Symfony needs.

This project includes:
* Symfony v4+
* PHP 7.1
* Nginx
* MySQL 5.7

## Installation

* Clone and/or fork this repository
* Edit the environment files listed here:
    * `.env.example`
    * `symfony/.env.example`
* Copy them:
    * `cp -v .env.example .env`
    * `cp -v symfony/.env.example symfony/.env`
* Run composer `cd symfony && composer install`
* Run `docker-compose up -d`
* Add the NETWORK_GATEWAY IP address to your hosts file. E.G `sudo echo "symfony.local 172.28.5.254" >> /etc/hosts`

## Environment Settings

These settings pertain to the Docker .env file which is located in the root of the project: `.env` or `.env.example`

| Variable             | Description   |
| -------------------- |:--------------|
| NETWORK_GATEWAY      | The docker network gateway setting. This is the address you will be using to connect |
| NETWORK_SUBNET       | The docker network subnet settings |
| NETWORK_IP_RANGE     | The docker network IP address range that containers will be given addresses from |
| | |
| | |
| MYSQL_ROOT_PASSWORD  | MySQL root password |
| MYSQL_DATABASE       | MySQL database name |
| MYSQL_USER           | MySQL database username |
| MYSQL_PASSWORD       | MySQL database password |
| | |
| | |
| SYMFONY_PATH | The path on the HOST machine where the symfony directory is located. This can probably be left default |
| WEBROOT_PATH | The path of the webroot directory within the containers. This is likely to be /var/www/example.com |
| SERVER_NAME | The server name variable used within Nginx to identify your host. You should choose the same name you add to your hosts file |
| | |
| | |
| XDEBUG_ENABLE | Enable PHP xDebug, either 1 or 0 |
| XDEBUG_HOST | The remote host IP for xDebug. This should be the same as your NETWORK_IP_RANGE variable |
| XDEBUG_PORT | The xDebug port. This can be left as default in most cases |
| XDEBUG_KEY | The key for detecting connections with xDebug. |
| | |
| | |
| TIMEZONE | Your current timezone. E.G. "Europe/London" |