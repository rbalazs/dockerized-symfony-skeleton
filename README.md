127.0.0.1       app.docker

docker-compose up -d --build

docker-compose exec php composer install

docker-compose exec php /app/bin/console doctrine:query:sql "select 1;"

docker-compose logs -f 