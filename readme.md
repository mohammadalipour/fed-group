# Api-Auth

### This test create on Tow Version :
* Web
* Api

## Running

```html
1- docker run --rm -v $(pwd):/app composer install
2- cp .env.example .env
3-nano .env
```
```html
config db connection on .env file
    DB_CONNECTION=mysql
    DB_HOST=db
    DB_PORT=3306
    DB_DATABASE=api_auth
    DB_USERNAME=root
    DB_PASSWORD=123qwe
```
```
4-docker-compose up -d
5-docker-compose exec app php artisan key:generate
6-docker-compose exec app php artisan config:cache
```
* url : http://localhost:9000

```
7-docker-compose exec db bash
8- mysql> CREATE DATABASE api_auth;
9- mysql> mysql -u root -p
10- mysql> GRANT ALL ON api_auth.* TO 'root'@'%' IDENTIFIED BY '123qwe';
11- mysql> FLUSH PRIVILEGES;
12- mysql> EXIT;
13-exit
14-docker-compose exec app php artisan migrate

