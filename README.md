### Clone Repositório
````
git clone https://github.com/we2l/setup-docker-laravel.git
````

### Clone o projeto do laravel
````
git clone https://github.com/laravel/laravel.git app-laravel
````

### Copie os arquivos docker-compose.yml, Dockerfile e o diretório /docker para o seu projeto
````
cp -rf setup-docker-laravel/* app-laravel/
````

### Crie o arquivo .env
````
cp .env.example .env
````

### Atualize as variáveis de ambiente 
````
APP_NAME="App Laravel"
APP_URL=http://localhost:8000

DB_CONNECTION=postgres
DB_HOST=db
DB_PORT=5432
DB_DATABASE=laravel
DB_USERNAME=root
DB_PASSWORD=root

CACHE_DRIVER=redis
QUEUE_CONNECTION=redis
SESSION_DRIVER=redis

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379
````

### Suba os containers do projeto
````
docker-compose up -d
````

### Acesse o container do laravel
````
docker-compose exec app bash
````

### Instale as dependências do projeto
````
composer install
````

### Gere as keys do laravel
````
php artisan key:generate
````

Acesse o projeto no browser: http://localhost:8000