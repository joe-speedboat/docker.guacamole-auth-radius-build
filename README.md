# docker.guacamole-auth-radius-build

This dockerfile is for easily building the latest radius-auth .jar for Apache Guacamole.

## Usage

- Clone the repo
```bash
git clone git@github.com:joe-speedboat/docker.guacamole-auth-radius-build.git
# git clone https://github.com/joe-speedboat/docker.guacamole-auth-radius-build.git

cd docker.guacamole-auth-radius-build
VERS=1.5.5
sed -i "s/ARG VERSION=.*/ARG VERSION=$VERS/" Dockerfile
docker build --tag guacamole-auth-radius .
docker run -d --name=guacamole-auth-radius guacamole-auth-radius
docker cp guacamole-auth-radius:/guacamole-auth-radius-$VERS.jar .
docker container prune -f
docker image prune -a -f
```
