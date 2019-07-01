## Laradock
Docker basic configuration with Nginx, Laravel, MySql and phpMyadmin containers tested. 
Laravel Basic Auth also added.
    
## Prerequisites
- docker
- git

## Install
- enter the console and go to your desired installation location, keep in mind that cloning or composing will create a new folder 
so don't make a new project folder in order to avoid excessive subtrees
- get the files by following one of these two methods:
###### Git (easier)
> `git clone https://github.com/spatariu/laradock.git` 
###### Composer
> if you choose to install via the composer you will need a functional php intallation (https://www.sitepoint.com/how-to-install-php-on-windows/), 
also the `php.ini` should contain this externsion `extension=fileinfo` (if it is not there add it at the end of the file), when you are done with this 
run `composer create-project spatariu/laradock`
- go to `laradock/laradock` subfolder and execute `docker-compose up -d nginx phpmyadmin` (it creates all the containers' links and also brings up 
the additional required containers - php-fpm - mysql - workspace).
- check if your containers are up by runnning `docker ps`, go to the workspace container to start interacting with your project 
with the following command: `docker exec -it laradock_workspace_1 bash` (if you have a different name for your workspace container type that one)
- run `composer update` once you are inside the `workspace` container
- now Laravel should be up and running on http://localhost:80 and phpMyadmin on http://localhost:8080/ (credentials mysql/root/root), if you are on
a VPS replace `localhost` with your public IP
- if you got any rights issues on Linux run `chmod -R 777 storage` and` chmod -R 777 bootstrap/cache`
- you can bring up other laradock available containers if required by using again `docker-compose up -d container_name1 container_name2` (in the 
project's `laradock/laradock` subfolder you can see the available containers' names).