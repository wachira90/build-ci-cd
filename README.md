# Build CI/CD Jenkins with docker

I don't want to install go in my jenkins container, I decided to use docker to build it so that the Jenkins container does only one thing.

## Using docker

```sh
docker build -t jenkins-with-docker .
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock -v /tmp/home:/var/jenkins_home -p 8080:8080 -p 50000:50000 -u root --privileged jenkins-with-docker docker -v
```

## Using docker-compose

```sh
docker-compose up -d

Starting dockerized-jenkins-with-docker_jenkins_1 ... done

docker-compose exec jenkins docker -v

Docker version 18.09.5, build e8ff056dbc
```