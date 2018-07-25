---
layout: post
title:  "Set up docker on Ruby on Rails application"
date:   2018-07-25 09:23:58 +0545
categories: tutorials
---

Some file required are:
dockerfile # install scripts
.dockerignore # ignore while pushing the code
.env # list env vars
docker-compose.yml # run the processes, containers and apps

Some useful commands:
docker-compose up # install 
docker-compose --build # build 

docker container ls # to see container list
docker ps # to see all the processes

docker-compose stop # to stop all the processes, so instead of killing all the container and processes you can run it and later on you can restart again

docker-compose run --rm website rake db:create db:migrate # website is the services to run rails app

sudo docker run -i -t <image/id> /bin/bash

docker-compose run app rake db:migrate db:seed RAILS_ENV=production
