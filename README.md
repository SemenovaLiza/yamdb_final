# Api Yamdb
![workflow badge for yamdb project](https://github.com/SemenovaLiza/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
### *Description*
This project is an extended version of the [api_yamdb](https://github.com/SemenovaLiza/api_yamdb) project, which allows you to manage the project on a remote server.
### *Technologies*
- Python 3.7
- Django 3.2.16
- django rest framework 3.12.4
- django rest framework-simplejwt 4.7.2
- PostgreSQL
- Docker 20.10.23
###### *The rest of the technologies can be found in the requirements.txt file*
### *How to launch a project*
Using terminal change the current working directory to the location where you want the cloned directory.

Clone the repository to your local machine:
```
git clone git@github.com:SemenovaLiza/api_yamdb.git
```
Go to the remote server and install docker:
```
ssh login@remote.server.pub.ip
sudo apt install docker.io
```
Install Docker Desktop and run it, install install the compose plugin on your remote server:
```
DOCKER_CONFIG=${DOCKER_CONFIG:-$HOME/.docker}
mkdir -p $DOCKER_CONFIG/cli-plugins
curl -SL https://github.com/docker/compose/releases/download/v2.17.2/docker-compose-linux-x86_64 -o $DOCKER_CONFIG/cli-plugins/docker-compose
```
Apply executable permissions to the binary:
```
chmod +x $DOCKER_CONFIG/cli-plugins/docker-compose
```
or, if you chose to install Compose for all users:
```
sudo chmod +x /usr/local/lib/docker/cli-plugins/docker-compose
```
Verify that docker-compose was installed correctly:
```
docker compose version
```
Copy *docker-compose.yaml* and *nginx/nginx.conf* from the infra directory to the remote server:
```
scp docker-compose.yml <login>@<host>:/home/<login>/docker-compose.yml
scp nginx.conf <login>@<host>:/home/login>/nginx.conf
```
Make a file using this pattern:
```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password
DB_HOST=db
DB_PORT=5432
```
### *Author*
Semenova Elizaveta
