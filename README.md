# Docker for Building a Local Development Environment

This project provides a basic Docker setup, for building a local development environment for Zend Expressive, and other PHP, application development.

## Why?

Why?
Good question.
But easy to answer.
The intent is to provide a starting point for developers to get up and running quickly, using Docker, to build a local development environment.
If you’d like much more background as to why, [checkout this tutorial on Master Zend Framework](http://www.masterzendframework.com/docker-development-environment/).
It lays out, much more comprehensively, the reasons why this is a good thing to do.

## Installation

To get up and running, after cloning the repository:

1. Install Docker. If you’re running a Linux distribution, use its package manager. If you’re using either macOS or Windows, download the respective Docker package installers: [Docker for Mac](https://docs.docker.com/docker-for-mac/) or [Docker for Windows](https://docs.docker.com/docker-for-windows/).

2. Add the cloned files to the root of a Zend Expressive (or other PHP) project.

3. In `docker/nginx/default.conf` change the default document root setting, `root /PATH/TO/YOUR/DOCUMENT/ROOT;`, to suit your installation. More than likely, there will be a `public/` directory in your source. So change the setting to be `root /var/www/html/public;`.

4. Build the configuration by running: `docker-compose up -d`.

### Check That Everything Is Working

To check that the build is working, run `docker-compose ps`.
This should give you output similar to the below.

```console
               Name                             Command             State               Ports
---------------------------------------------------------------------------------------------------------
dockerforlocaldevelopment_mysql_1     docker-entrypoint.sh mysqld   Up      3306/tcp
dockerforlocaldevelopment_nginx_1     nginx -g daemon off;          Up      443/tcp, 0.0.0.0:8080->80/tcp
dockerforlocaldevelopment_php_1       php-fpm                       Up      9000/tcp
dockerforlocaldevelopment_testing_1   php-fpm                       Up      9000/tcp
```

If you’d like to see more detailed information, check the log file by running `docker-compose logs`.
To check that the files are inside the container, run the following command, substituting `dockerforlocaldevelopment` to match your directory name:

```console
docker exec -it dockerforlocaldevelopment_nginx_1 ls -lahrt /var/www/html
```

## Contributing

See the [CONTRIBUTING](CONTRIBUTING.md) file.

## License

This project is licensed under the [MIT License](/LICENSE).
