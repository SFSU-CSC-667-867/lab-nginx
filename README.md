# Building and serving static files

For serving static files, express is not a good choice. In production, you will need a static file server like Ngnix or Appache.

## Nginx
https://www.nginx.com/resources/wiki/start/topics/examples/full/



Map a volume on your local machine to its serve path.
This is the default internal mount location: /usr/share/nginx/html
```
docker run -d -p 8000:80  -v your/build/path:/usr/share/nginx/html:ro nginx
```

Build a docker container :
```
docker build -t nginx-app .
```
## launch as a stack service
```
docker stack deploy -c docker-compose.yml ngnix-service
```

## ssh into a docker container
```
docker exec -it containerId sh
```

Default conf loction: `/etc/nginx/nginx.conf`

## FOR LAB
Build a new dockerfile that is a self contained react app


Push to dockerhub.


Modify docker-compose file to serve a react app as a service.


Next add a custom nginx.conf file so that you can serve static files off your machine on the /static-content directory.

