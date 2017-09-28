# Docker ProxySQL image

## About this image

This docker image is based on *debian:stretch* and contains both (*proxy-sql*)(https://github.com/sysown) and (*dumb-init*)(https://github.com/Yelp/dumb-init).

## Supported tags and respective `Dockerfile` links

-	[`1.4` (*Dockerfile*)](https://github.com/anexia-it/docker-proxysql/blob/master/1.4/Dockerfile)


## Build and update process

This image is built automatically whenever a new commit is pushed to this repository or the *debian:stretch* base image is updated.

## Run

```
docker run -v /path/to/proxysql.cfg:/etc/proxysql.cfg anexia/proxysql:1.4
```

## Configuration file

You can find some examples of the `proxysql.cfg` in the official repository: https://github.com/sysown/proxysql/blob/master/doc/configuration.md

## Thanks

Based on original work by [PrimaIT](https://github.com/primait/docker-proxysql) and [Signal 18](https://github.com/signal18/docker-proxysql)
