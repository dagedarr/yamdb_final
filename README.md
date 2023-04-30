# yamdb_final
![example workflow](https://github.com/dagedarr/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

# Примеры запросов:
- http://51.250.0.37/api/v1/
- http://51.250.0.37/admin
- http://51.250.0.37/redoc

Возможности API: 
- регистрация пользователей 
- получение токенов для доступа 
- просмотр, публикация, редактирование, удаление записей 
- комментирование записей 
- реализована пагинация 

# Установка

1. Клонируйте репозиторий
```
git clone https://github.com/dagedarr/yamdb_final.git

cd api_yamdb/
```
Если вы не используете Git, то вы можете просто скачать исходный код репозитория в ZIP-архиве и распаковать его на свой компьютер.

2. Создайте виртуальное окружение и активируйте его
```
python -m venv venv
source venv/bin/activate
```
3. Установите зависимости
```
pip install -r requirements.txt
```

4. Запустите docker-compose 
```
cd ../infra
docker-compose up -d --build 
```

5. Выполните по очереди команды
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input
docker-compose exec web python manage.py loaddata
```
Откройте браузер и перейдите по адресу http://127.0.0.1:8000/admin/. Введите имя пользователя и пароль администратора, чтобы войти в панель управления.

# Готово!
Вы успешно установили Проект YaMDb и готовы начать его использовать!