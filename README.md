# spring-example

This is an example [spring
boot](https://spring.io/projects/spring-boot) API server, along with
Makefile integration for [d.rymcg.tech](d.rymcg.tech) (Docker),
installed as a microservice deployed behind the Traefik web proxy.

This project was initially generated using the
[start.spring.io](https://start.spring.io/) creation tool and
following the
[spring-boot-docker](https://spring.io/guides/topicals/spring-boot-docker/)
guide.

## Prerequisites

Create a Docker server, and install Traefik all according to the
README for [d.rymcg.tech](d.rymcg.tech). Make sure to install the
[whoami](https://github.com/EnigmaCurry/d.rymcg.tech/tree/master/whoami)
service first, to test that Traefik is working properly, and then come
back here and follow the rest of these steps to install the example
spring service.

Make sure that you clone d.rymcg.tech the exact way it says to in the
README, to the path: `${HOME}/git/vendor/enigmacurry/d.rymcg.tech`,
which is a conventional vendor-neutral path structure that this
configuration expects to be the same on every machine (but if you
really want to clone it someplace else, just edit the
[Makefile](Makefile) and change the `ROOT_DIR` variable accordingly.)

## Setup

Clone this project someplace and change into that directory:

```
git clone https://github.com/EnigmaCurry/spring_example \
  ${HOME}/git/spring-example
cd ${HOME}/git/spring-example
```

## Configure

To create the configuration file, run the configuration wizard, which
will create a file named like `.env_{DOCKER_CONTEXT}_{INSTANCE}`. The
default configuration is copied from the included
[.env-dist](.env-dist) file.

Run:

```
make config
```


## Install

Run:

```
make install
```

(If you change the configuration or the build, you can re-run `make
install` as many times as you want, and it will reinstall it using the
new config/build, but keeping the existing data).

## Show the service logs

```
make logs
```

## Open the example URL in your browser

```
make open
```

## Stop the service

```
make stop
```

## Delete the service and all of its data

```
make destroy
```
