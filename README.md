./init-letsencrypt.sh
docker-compose up --build
docker-compose -f docker-compose.yml -f docker-compose.staging.yml up -d
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d

Source:
https://medium.com/@pentacent/nginx-and-lets-encrypt-with-docker-in-less-than-5-minutes-b4b8a60d3a71

chmod +x init-letsencrypt.sh

docker-compose logs -f nginx
docker-compose exec backend /bin/sh -c 'echo $DJANGO_ENV'

stop:
docker stop $(docker ps -a -q)
remove:
docker rm $(docker ps -a -q)

docker-compose up --build -d backend
docker logs -f ef74d3452807

docker exec -it ef74d3452807 /bin/sh
chmod +x init.sh
