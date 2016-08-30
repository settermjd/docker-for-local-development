# Docker for Building a Local Development Environment

This project provides a basic Docker setup, for building a local development environment for Zend Expressive, and other PHP application development.

## Why?

Why? Good question. But easy to answer. The intent is to provide a starting point for developers to get up and running quickly, using Docker, to build a local development environment. If you’d like much more background as to why, [checkout this tutorial on Master Zend Framework](http://www.masterzendframework.com/docker-development-environment/). It lays out, much more comprehensively, the reasons why this is a good thing to do.

## Installation

To get up and running, after cloning the repository, either install Docker using your package manager of choice, if you’re running a Linux distribution. If you’re using either Mac OSX or Windows, download the respective Docker package installers: [Docker for Mac](https://docs.docker.com/docker-for-mac/) or [Docker for Windows](https://docs.docker.com/docker-for-windows/).

After that, add the cloned file and directory to the root of a Zend Expressive (or PHP) project. Then, run `docker-compose up -d`. This will boot Docker and build the containers for you.

## Contributing

See the [CONTRIBUTING](CONTRIBUTING.md) file.

## License

This project is licensed under the [MIT License](/LICENSE).
