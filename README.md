## Запуск

	#1. Поднять Postgres
	docker compose up -d

	#2. Активировать venv
	source venv/bin/activate

	#3. Запустить Django
	python manage.py runserver
	
	(не получилось сделать 1 командой: docker-compose up --build
	из-за того что pip не может скачать пакеты с pypi.org)

## Доступные URL

	#1 Тесты: pytest -v
	#2 API: http://127.0.0.1:8000/api/
	#3 Swagger UI: http://127.0.0.1:8000/api/docs/
	#4 Админка: http://127.0.0.1:8000/admin/

## Стек

	- Python 3.11+
	- Django 6.1
	- Django REST Framework
	- PostgreSQL 16
	- JWT (`djangorestframework-simplejwt`)
	- Swagger (`drf-spectacular`)
	- Docker + Docker Compose
	- pytest + pytest-django

## Функционал

	- Пользователи: регистрация, авторизация (JWT), профиль, баланс
	- Товары: CRUD (чтение — всем, запись — только админам)
	- Корзина: добавление, изменение количества, удаление
	- Заказы: создание из корзины с проверкой остатков и баланса, транзакционность
	- Email-уведомления после заказа
	- Логирование в файл
