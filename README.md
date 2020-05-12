# Docker Compose

## Installation
- `$ brew install docker-compose && docker-compose --version`

## Steps
- `$ mkdir docker-compose-demo && cd docker-compose-demo`
- Create "docker-compose.yml" file and add services and their properties as you need
- `$ docker-compose config`  // To validate the file
- `$ docker-compose up`    // add detach mode "-d" once you're familiar with docker-compose
- Watch the logs carefully & if ever thing went smooth then you can see something like below containers up and running
- `$ docker-compose ps`
    ```
    CONTAINER ID        IMAGE                                COMMAND                  CREATED             STATUS              PORTS                    NAMES
    d00f1118e7e8        amarnath510/docker-my-tomcat-image   "catalina.sh run"        28 seconds ago      Up 27 seconds       0.0.0.0:8181->8080/tcp   docker-compose-demo_tomcat-compose_1
    8442852ef31c        amarnath510/mysql-5.6-docker-image   "docker-entrypoint.s…"   28 seconds ago      Up 27 seconds       0.0.0.0:3306->3306/tcp   docker-compose-demo_mysql-compose_1
    ```

## Check Services
- `$ cd <proj-directory> && docker ps` or `$ docker-compose ps` (from anywhere)
- Validate Tomcat: `Hit http://localhost:8181/`
- Validate MySQL: 
    - `$ docker container exec -it 8442852ef31c bash`
    - `$# mysql -uroot -pdev`
    - `$# show databases;`  // should see company db

## Stop all
- `$ docker-compose down`
- You can also do individually like `$ docker container stop <con-name-or-id>`

## Reference
- Usually every official image will have docker-compose section. Go to the official page in docker-hub and search for "compose"
- [Simple Explanation](https://www.youtube.com/watch?v=HUpIoF_conA)