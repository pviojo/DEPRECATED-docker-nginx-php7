Nginx + PHP 7 + FPM
============================

## Getting started

### Prerequisites

* [Docker](https://store.docker.com/search?offering=community&type=edition)
* [Docker-compose](https://docs.docker.com/compose/install/)


### Installing

Create a src folder and put your code there (example: index.php).

Navigate to http://localhost:8080

Enjoy


## Configuration

* Nginx port can be changed in docker-compose.yml
* Nginx configuration in docker/nginx/conf.d/default.conf
* PHP configuration in docker/php-fpm/php.ini (or docker/php-fpm/php.ini-production)

It comes with some PHP extensions installed. See docker/php-fpm/Dockerfile for details

## Running

As usual

```
docker-compose up -d
```

## Building the images (just in case)

```
docker-compose build
```

## Authors

* Pablo Viojo, [pviojo@gmail.com](mailto:pviojo@grouponlatam.com), [https://tiopaul.io](https://tiopaul.io)

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT)



