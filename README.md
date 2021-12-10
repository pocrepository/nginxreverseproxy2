# nginxreverseproxy2
 prerequisites: 
 
 1. Docker Ce, Ubuntu 18.04;

2. Enable port 80 (http) & port 443 (https) on host machine

3. add the following to /etc/hosts file on your vm

    your-server-ip   website1.test

    your-server-ip   website2.test
    
 # Steps (****) & Commands


*****Clone this repository on your local computer

git clone https://github.com/pocrepository/nginxreverseproxy2.git

*****go into directory website1

cd website1

******build and compose for website1, website2 and proxy

docker-compose build

docker-compose up -d

cd ..

cd website2

docker-compose build

******test reverse proxy using curl command
curl website1.test
curl website2.test

Note: the output of curl commands should display html code. example shown below.
<!DOCTYPE html>
<html>
<head>
<title>First Website to test NGINX REVERSE PROXY</title>
</head>
<body>
<h1>Hello! This is my first website.</h1>
</body>
</html>


docker-compose up -d

cd ..

cd proxy

docker-compose build

docker-compose up -d

Reference: adapted from https://www.atlantic.net/dedicated-server-hosting/how-to-deploy-nginx-reverse-proxy-in-docker-on-ubuntu-20-04/

