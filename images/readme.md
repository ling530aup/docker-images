* To push docker image to docker hub
```$xslt
docker login --username ling530aup
docker tag #{image-id} ling530aup/mysql-repo
docker push ling530aup/mysql-repo
```
* To build the image  
cd to docker file dir and run  
`docker build -t datadealer .`