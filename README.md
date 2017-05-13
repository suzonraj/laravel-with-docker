# Laravel With Docker
Clean install of Laravel **5.4**, with support for Docker. Simply run ` sudo docker-compose up` from the project root.

### Note
The **node_modules**, and **vendor** directories are not being tracked. This is by design. You must run `composer install` and `npm install` from your project root to pull in your dependencies. You can install these tools locally (recomended), or add them to the build script at `./deploy/web.docker` and access them from inside the web container. More documentation and instruction on this to come in the near future.

# Environment Settings

The following environment variables must be set. This will probably be added to the docker-compose script in the future, but until then the following .env should be placed in your project root:
```
APP_ENV=local
APP_KEY=base64:0/RLFKE+S8qQlhsVab8TVNSKFy4/y+xAtbuIWVwi6IA=
APP_DEBUG=true
APP_LOG_LEVEL=debug
APP_URL=http://localhost:8080

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=33061
DB_DATABASE=dockerApp
DB_USERNAME=root
DB_PASSWORD=secret

CACHE_DRIVER=redis
SESSION_DRIVER=file
QUEUE_DRIVER=sync

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=63791

MAIL_DRIVER=smtp
MAIL_HOST=mailtrap.io
MAIL_PORT=2525
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
```