# laravel:latest
docker build -t izcss21/laravel:dev .
docker run --name mylaravel izcss21/laravel:dev

# laravel:prod
docker build -t izcss21:laravel:prod laravel -f laravel/Dockerfile.prod
