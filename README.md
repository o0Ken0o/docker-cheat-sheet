# A list of docker commands
It is to document a list of docker commands I have used throughout development.

Assume we have a project structure like this.

```
.
├── app
│   ├── Dockerfile
│   ├── db.sqlite3
│   ├── entrypoint.sh
│   ├── hello_django
│   │   ├── __init__.py
│   │   ├── asgi.py
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   ├── manage.py
│   └── requirements.txt
└── docker-compose.yaml
```

```zsh
# build the image
# exec under root dir
$ docker-compose build
```

```zsh
# list active containers
# run anywhere
$ docker ps
```

```zsh
# list all containers
# run anywhere
$ docker ps -a
```

```zsh
# start the container in detached mode
$ docker-compose up -d
```

```zsh
# stop the container
$ docker stop <container_id/container_name>
```

```zsh
# start the container
$ docker start <container_id/container_name>
```

```zsh
# start an interactive bash session
# your container need to support bin/bash
# otherwise, some error like this. 
# exec: "/bin/sh": stat /bin/sh: no such file or director
$ docker exec -it <container_id/container_name> "/bin/bash"
```

```zsh
# start a psql session
# your docker-compose.yaml should have a session called db
$ docker-compose exec db psql --username=hello_django --dbname=hello_django_dev
```

```zsh
# list volumes
$ docker volume ls
```

```zsh
# inspect a volume
# it may come in handy if you want check your volumes
$ docker volume inspect <volume>
```