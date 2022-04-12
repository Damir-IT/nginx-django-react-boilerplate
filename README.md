# nginx-django-react-boilerplate
It is a Telegram Bot application written using Django + React + Nginx + LetsEncrypt + PostgreSQL + Redis + Celery.
I used https://github.com/saasitive/django-react-boilerplate and made some improvements.
# Dev Project Setup
1.  ```git clone``` via ssh
2. Install docker и docker-compose by this tutorials:
- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-20-04-ru
- https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04-ru
3. Start project via command
```./bin/dev```
4. After a succesful launch you will see project's main page on your ```localhost``` address. 
  You should also check ```localhost/api``` and ```localhost/admin```, to ensure the drf and django are there. 
5. Go to  ./frontend and run ```npm i```
  **NB!** It should be run locally and not in docker
7. Run ```nmp start```  in ./frontend and if you did everything correctly you would see the project's main page on  ```localhost:3000``` 
  **NB!** During dev you should only work with frontend on this port, because ```localhost``` is not updated upon changes in code.   
  ```localhost:3000``` uses webpack, thus it is

# Prod Project Setup
1. Change all test.domain occurances in your project files to your domain
2. Run ```./init-letsencrypt.sh``` and make sure you don't have any errors
3. On line 12 in init-letsencrypt.sh change staging to 0 
4. Run ```./init-letsencrypt.sh``` and wait till you get ssl
5. Stop all docker containers
6. Start project using ```./bin/dev```


# Bin files
- ```./bin/dev``` - dev start up
- ```./bin/lint``` - linters
- ```./bin/manage``` - alias for python3 manage.py, accepts arguments
- ```./bin/shell``` - alias for python3 manage.py shell
- ```./bin/prod``` - prod start up
