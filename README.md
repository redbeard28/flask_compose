# flask_compose

```

+------------+         +--------------+     +-----------+
|            |         |              |     |           |
+  gunicorn  +---------+  flask app   +-----+   redis   |
|            |         |              |     |           |
+------------+         +--------------+     +-----------+

```

## Environments setup

please install `docker` and `docker-compose`.
I have already a HAProxy and a reverse proxy nginx installed on my envirment
This setup will do a git clone of https://github.com/redbeard28/api-redbeard28.git
This will install my first flas-rest api.

## Quick start

### build and up

```sh
$ git clone https://github.com/redbeard28/flask_compose
$ cd flask_compose
$ docker-compose build
$ docker-compose up -d
Starting dockercomposeflask_redis_1 ... done
Starting dockercomposeflask_web_1 ... done
```

Check the service running information

```sh
$ docker-compose ps
           Name                         Command               State           Ports
--------------------------------------------------------------------------------------------
dockercomposeflask_redis_1   docker-entrypoint.sh redis ...   Up      6379/tcp
dockercomposeflask_web_1     /runserver.sh                    Up      0.0.0.0:8000->8000/tcp
```

Check the web service directly on flask port.

```sh
$ curl http://IP_ADDR:5000
```

### stop the service

```sh
$ docker-compose stop
Stopping dockercomposeflask_web_1   ... done
Stopping dockercomposeflask_redis_1 ... done
```

## Sources
Original work from [xiaopeng163](https://github.com/xiaopeng163/docker-compose-flask)