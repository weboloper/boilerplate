./init-letsencrypt.sh
docker-compose up --build
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
docker-compose -f docker-compose.yml -f docker-compose.staging.yml up -d

Source:
https://medium.com/@pentacent/nginx-and-lets-encrypt-with-docker-in-less-than-5-minutes-b4b8a60d3a71

chmod +x init-letsencrypt.sh
