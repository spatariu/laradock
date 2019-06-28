## Laradock
Docker basic configuration with Nginx, Laravel, MySql and phpMyadmin containers tested. 
Laravel Basic Auth also added.
    
## Prerequisites
- docker
- git

## Install
- enter the console and go to your desired installation folder
- git clone https://github.com/spatariu/laradock.git or by composer
- go to laradock subfolder and execute 'docker-compose up -d nginx phpmyadmin' (it creates all the containers' links and also brings up the additional required containers - php-fpm - mysql - workspace)
- you can go to workspace container to start interacting with your project with the following command: 'docker exec -it laradock_workspace_1 bash'
- you can bring up other laradock available containers if required
