# WPDev
Docker based development environment for WordPress. It includes MySQL(5), Nginx, PHP(7.2) and Memcached.

## Dependencies

* Docker - ([windows](https://docs.docker.com/docker-for-windows/install/), [mac](https://docs.docker.com/docker-for-mac/install/))
* Docker-Compose - ([install](https://docs.docker.com/compose/install/))

## Usage

First, clone this repo to your desired location:

`git clone https://github.com/PeterBooker/wpdev.git local-site-name`

Next, from the newly created directory, start up the Docker containers:

`docker-compose up`

You can stop and start the containers afterwards with:

`docker-compose stop` and `docker-compose start`

You can also remove the containers with:

`docker-compose --rmi=all -v`