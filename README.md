# API_Yatube

REST API для сети блогов Yatube. Работает со всеми модулями социальной сети Yatube: постами, комментариями, группами, подписчиками. Поддерживает методы GET, POST, PUT, PATCH, DELETE. Работает с JWT-токенами.

Стек: Python 3.7, Django Rest Framework, Simple-JWT

# Как запустить проект:

- Клонируйте репозитроий с проектом:
```
git clone git@github.com:LazarevaKate/api_yatube.git
```
- В созданной директории установите виртуальное окружение, активируйте его и установите необходимые зависимости:
```
python3 -m venv venv
. venv/bin/activate
pip install -r requirements.txt
```

- Выполните миграции:
```
python manage.py migrate
```

- Создайте суперпользователя:
```
python manage.py createsuperuser
```
- Запустите сервер:

```
python manage.py runserver
```

Ваш проект запустился на http://127.0.0.1:8000/

Аутентификация
Выполните POST-запрос localhost:8000/api/v1/token/ передав поля username и password.

API вернет JWT-токен в формате:

{
    "refresh": "ХХХХХХХХХХХ",
    "access": "ХХХХХХХХХХХХ"
}
Токен вернётся в поле access, а данные из поля refresh нужны для обновления токена

При отправке запроcов передавайте токен в заголовке Authorization: Bearer <токен>

