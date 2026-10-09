## Установка Laravel (пустой проект)

Обновление пакетного менеджера Composer до последней стабильной версии.

```bash
composer self-update
```

Скачивание и установка чистого каркаса Laravel в текущую директорию
```bash
composer create-project laravel/laravel .
```


Настройка приложения для работы в качестве API, установка Laravel Sanctum для аутентификации
```bash
php artisan install:api
```

Публикация файла конфигурации для настройки CORS-политики (разрешение cross-origin запросов к вашему API  с других доменов/фронтенда).
```bash
php artisan config: publish cors
```

Создание символической ссылки из публичной папки **public/storage** в закрытую папку **storage/app/public**.
Это необхожимо, чтобы загруженные файлы были доступны по прямой ссылке из браузера.

```bash
php artisan storage:link
```

Создание файла **.htaccess** в корне проекта, чтобы перенаправить все запросы в папку **pubic**.

```php
// Включает мощдуль mod_rewrite в веб-сервере
RewriteEngine on
// Правило, которое берет абсолютно любой запрошенный URL и незаметно для пользователя перенаправляет его в папку public
RewriteRule ^(.*)$ public/$1 [L]
```


## Установка Laravel проекта из репозитория

Откройте коносль домашней директории сайтов.
Выполните клонировние репозиторя в домашнюю директорию сайтов и установите все зависимости. 

```bash
git clone https://github.com/maksmarkis/learn-laravel-13.git
composer install
```
Скопируем файл .env из файла **.env.example**.

```bash
copy .env.example .env
```

Сгенерируем ключ шифрования 

```bash
php artisan key:generate
```

Выполните миграцию

```bash
php artisan migrate --seed
```




























































