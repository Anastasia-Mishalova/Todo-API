# ToDo API
Простой REST API для управления списком задач на Laravel

## Технологии
- PHP
- Laravel
- MySQL
- JSON для запросов и ответов

---

## Маршруты API

### 1. Получить список всех задач
Пример запроса: GET http://127.0.0.1:8000/api/tasks

### 2. Получить одну задачу по id
Пример запроса: GET http://127.0.0.1:8000/api/tasks/1

### 3. Создать новую задачу
Пример запроса: POST http://127.0.0.1:8000/api/tasks
В Body:  
```
{
    "title": "task 1",
    "description": "description task 1",
    "status": "pending"
}
```

### 4. Обновить существующую задачу
Пример запроса: PUT http://127.0.0.1:8000/api/tasks/1
Content-Type: application/json
В Body:  
```
{
  "description": "update description task 14",
}
```

### 5. Удалить задачу
Пример запроса: DELETE http://127.0.0.1:8000/api/tasks/1

---

## Установка и запуск

### 1. Клонировать репозиторий
```
git clone https://github.com/Anastasia-Mishalova/Todo-API.git
cd Todo-API
```

### 2. Установка PHP-зависимостей
```
composer install
```

### 3. Настройка окружения
Скопируйте пример файла окружения и отредактируйте .env (укажите данные БД и прочие параметры):
```
cp .env.example .env
```

Измените в .env данные на эти и подставьте название своей БД, имя вашего аккаунта и пароль:
```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=todoapi    #название бд
DB_USERNAME=root       #имя пользователя бд
DB_PASSWORD=''         #пароль пользователя бд
```

### 4. Применение миграций
```
php artisan migrate
```

### 5. Запуск локального сервера
```
php artisan serve
```

### 6. Для тестирования маршрутов перейдите в Postman и выполните команды из примеров выше

---

### Валидация полей
- `title` — обязательно, строка  
- `description` — необязательно, строка  
- `status` — обязательно, одно из значений: `pending`, `in_progress`, `done`

