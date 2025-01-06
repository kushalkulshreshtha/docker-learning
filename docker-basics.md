<h1>Docker Basics</h1>

docker commands are of the format 'docker _main-command_ _sub-command_' for eg. docker container run
Old format was just 'docker _command_' like docker run. It will still work as docker is backward compatible, but better to use new method.

* docker info
  * prints information like version etc
* docker container run _name_ : for eg docker container run nginx
  * Looks for an image called nginx in cache, if not found then downloads it from docker hub
  * Then runs the container
* docker container run --publish 80:80 nginx
  * forwards the localhost port 80 to the container port 80 where nginx is running
* docker container ls
  * lists all the active containers
* docker container ls -a
  * lists all the existing containers (active or inactive) 
* docker container run --detach nginx
  * runs docker in the background, and the command line is available for the next set of code
* docker container run --publish 80:80 --detach --name webhost nginx
  * create with the name 'webhost' instead of the default name
  * forwards the port localhost 80 to container 80
  * runs in the background (--detach)
* docker stop _id_
* docker container logs webhost
  * logs information in the name webhost
* docker container rm _id initials array_ like docker container rm 3ed 513m
  * removes all the containers with the ids' initials mentioned
  * does not remove active containers even if you specify the id as a safety measure
  * also works with names
* to remove the active containers as well, we need to force it with -f like docker container rm -f webshost
* docker container top webhost
  * lists all the running processes
