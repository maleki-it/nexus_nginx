
# Nexus behind Nginx   
Nexus OSS behind Nginx with SSL with Docker

### Install dependencies  
Docker and Docker Compose
~~~bash  
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh
~~~
Clone the project in /opt/ 

~~~bash  
  git clone https://github.com/maleki-it/nexus_nginx.git
~~~

Go to the project directory  

~~~bash  
  cd /opt/nexus_nginx
~~~

Change YourDomainName 
~~~bash  
vim docker-compose.yml 
#edit YourDomainName with your acutal Domain name
vim nginx.conf
#edit YourDomainName with your acutal Domain name
~~~
## Install  Nexus and Nginx & Certbot
~~~bash
docker compose up -d 
~~~

### Get SSL Certification with Certbot
 getting SSL certification without use public IP 
~~~bash
docker exec -it certbot certbot -d YourDomainName --manual --preferred-challenges dns certonly
~~~
after this certbot ask you to set a txt dns record on your dns provider
do it to get certs

restart nginx
~~~bash
docker restart nginx
~~~
## Contributing  

Contributions are always welcome!  

## License  

[MIT](https://choosealicense.com/licenses/mit/)
