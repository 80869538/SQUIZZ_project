# SQUIZZ_Project development environment

This project is the integration of frontend, backend and database. It is conducted so to realize continuous integration, automatic testing and automatic testing.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

In order to run these containers you'll need docker installed.

* [Windows](https://docs.docker.com/windows/started)
* [OS X](https://docs.docker.com/mac/started/)
* [Linux](https://docs.docker.com/linux/started/)

Open Docker Destop

You must have access to both referenced repo
 * https://github.com/SinkableFish/COMP90082-Software-Project.git
 * https://github.com/ymh357/Software-Project.git

### Installing

```shell
git clone https://github.com/80869538/SQUIZZ_project.git
```

```shell
cd SQUIZZ_project
git submodule update --init
git submodule update --init --recursive
```
Checkout docerized branch
```shell
cd Frontend
git branch checkout remotes/origin/logout
cd ..
cd Backend 
git checkout remotes/origin/dockerization
cd ..
```
Build images
```shell
docker-compose build
```

Start services 
```shell
docker-compose up
```

If any node fail to start, try removing the running instance from docker dashboard, and run command:

```shell
docker-compose up --build
```

## Develop

webpack dev server can be accessed at http://localhost:3000. If dosen't work, try to kill the process who are lisening on 3000 or try accessing http://0.0.0.0:3000.

Flask sever  can be accessed at http://localhost:5000.

Connect to Mysql database by command

```shell
mysql -h localhost -P 3306 --protocol=tcp -u root -p
squizz
```
Try change -h from localhost to 0.0.0.0 if not work. If still get Access denied error, it's likely you have mysql running on localhost. Try shut down local Mysql sever, if you have to access container database directly(frontend server, backend server and database runing under the same LAN, thus they can always access each other from inside)

## Continuous Integration

This project is built and tested automatically upon each pull request by CircleCI(https://circleci.com/docs/2.0/about-circleci/#section=getting-started)

## Automatic develoyment

Project will be deployed on AWS E2 sever.

## Acknowledgments

* Hat tip to anyone whose code was used


