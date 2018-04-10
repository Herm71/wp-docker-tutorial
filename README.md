# Dockerized WordPress for Development

This is a WordPress [Docker](https://www.docker.com/) container setup for local development. This setup was put together based on the [WordPress Developer's Intro To Docker](https://codeable.io/wordpress-developers-intro-to-docker-part-two/) series at [codeable](https://codeable.io). This project was developed as a way to learn Docker in general and, specifically, how I can incorporate it into my [WordPress](https://wordpress.org/) development workflow.

## Requirements

* [Docker](https://www.docker.com/)
* [Docker Compose](https://docs.docker.com/compose/)

## Features installed locally

* [Nginx](https://www.nginx.com/) web server serving at [localhost:8080](http://localhost:8080)
* PHP
* MYSQL: MariaDB 5.5
* [WP-CLI](https://wp-cli.org/)
* Local `wp-content` folder
* Local `mysql` folder
* Local `redis` folder

## Installation

### Clone repository

Clone this repository into a new project directory and enter the new directory.

```console
git clone git@github.com:Herm71/wp-docker-tutorial.git my-project && cd my-project
```

### Create local directories

Create two empty directories, one for `mysql` and one for `redis`

```console
mkdir mysql
```

The `mysql` directory will contain the local copy of the wp database.

```console
mkdir redis
```

### Create local `wp-content` directory

If this is a brand-new project, you can simply copy the `wp-content` directory from the [official WordPress repository](https://github.com/WordPress/WordPress) by cloning it into a new directory and copying the `wp-content` directory into your project directory. If you have an existing project, use its `wp-content` directory.

### Fire it up!

```console
$ docker-compose build
# Wait a while ...
$ docker-compose up
```

You should now have a fresh WordPress install at [http://localhost:8080](http://localhost:8080). Complete the [Famous 5-Minute Installation](https://codex.wordpress.org/Installing_WordPress#Famous_5-Minute_Installation), log in, and you're off to the races! In order to stop or shut down the instance, hit `ctrl-c`. To restart the instance, type `docker-compose up` again (it is not necessary to re-build the instance).

## Development
Now that you have a local `wp-content` directory, you can do all your development locally, clone, develop, and commit theme or plugin repos inside this local directory and they will be reflected in your dockerized WordPress site!