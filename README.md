# laravel:latest
docker build -t izcss21/laravel:dev .
docker run --name mylaravel izcss21/laravel:dev

# laravel:prod
docker build -t izcss21/laravel:prod . -f Dockerfile.prod

# nginx:prod
docker build -t izcss21/nginx:prod nginx -f nginx/Dockerfile.prod

# laravel com nginx e proxy reverso
docker network create laranet
docker run -d --network laranet --name laravel izcss21/laravel:prod
docker run -d --network laranet --name nginx -p 8080:80 izcss21/nginx:prod