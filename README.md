# PHP + Nginx docker image

[![](https://images.microbadger.com/badges/image/mtxr/docker-php-nginx.svg)](https://microbadger.com/images/mtxr/docker-php-nginx "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/mtxr/docker-php-nginx.svg)](https://microbadger.com/images/mtxr/docker-php-nginx "Get your own image badge on microbadger.com")

Minimal nginx + PHP7 image based on [Alpine Linux](https://hub.docker.com/_/alpine/).

## Building

You can easily build you docker image with some tunnings. Clone this repository and follow the instructions below.

`docker build -t my_image_name .`

With args:

`docker build --build-arg HOST_USER=mtxr HOST_UID=$UID -t my_image_name`

| Arguments | Usage | Default |
|---|---|---|
| `HOST_USER` | Setup the user (besides root). Eg. ls -hal will show this name for mounted volumes instead of 1000 | `user` |
| `HOST_UID` | Setup the user id for $HOST_USER. | `1000` |
| `INSTALL_PACKAGES` | Add alpine packages to the build. Eg. `php7-iconv php7-gd php7-gdm` | `""` |
| `APK_REPOSITORIES` | Url's to alpine repositories separed by `\n` | `""` |


## Running

On your terminal:

`docker run -p 80:80 -it my_iamge_name /bin/sh` or `docker run -d -p 80:80 -it my_iamge_name /bin/sh` to run as daemon.

Open your browser and navigate to `http://localhost`.

Voilà!

## Paths

| Description | Path |
|---|---|
| Public website | `/www/` |
| Nginx default server | `/sites/default.conf` |
| Nginx servers | `/sites/*` |
| Supervisor auto start | `/autostart/*` |
| PHP-FPM Pools | `/etc/php7/php-fpm.d/*` |

