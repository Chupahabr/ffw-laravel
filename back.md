Зайти в бд из контейнера
```
psql -U knowledge
```

Конект к бд
```
\c knowledge
```

Получить таблицы
```
\dt
```

Для коннекта через ide нужен лог пас из конфигов POSTGRES_USER и POSTGRES_PASSWORD

Зайти в консоль контейнера 
```
docker-compose exec postgres /bin/bash
```

----------------

Ларавелька.

Заходим в контейнер php-fpm и прописываем 
```
composer update
```

Перегрузить таблицы
```
php artisan migrate:refresh
```

Порядок миграций
```
php artisan migrate --path="database/migrations/2023_07_26_194735_create_images_table.php"
php artisan migrate --path="database/migrations/2023_07_26_195352_create_groups_table.php"
php artisan migrate --path="database/migrations/2023_07_26_195158_create_teams_table.php"
php artisan migrate --path="database/migrations/2023_07_26_194103_create_attachments_table.php"
php artisan migrate
```

Сгенерировать app key
```
php artisan key:generate
```

Сгенерировать фабрику
```
php artisan make:factory НазваниеФабрикиFactory -mНазваниеМодели
php artisan make:factory StatusesFactory -mStatuses
```

Получить случайный id элемента из базы
```
$randId = Statuses::get()->random()->id;
```

Сгенерировать seeds
```
php artisan migrate --seed
```
