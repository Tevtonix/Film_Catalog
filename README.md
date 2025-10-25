# Movies API

Краткое описание проекта
------------------------
RESTful-сервис на FastAPI для управления коллекцией фильмов.  
Поддерживает асинхронную работу с SQLite (aiosqlite), миграции через Alembic, валидацию данных Pydantic v2 и автоматическую генерацию OpenAPI-документации.

Основные возможности приложения
-------------------------------
* CRUD-операции с фильмами  
* Фильтрация по году и рейтингу  
* Сортировка по title, year, rating, id (возможен обратный порядок)  
* Пагинация (limit / offset)  
* Валидация входных данных на уровне Pydantic-моделей  
* Асинхронное взаимодействие с БД  
* Автоматические миграции схемы (Alembic)  
* 100 % покрытие основных сценариев pytest-тестами  

Технологический стек
--------------------
* Python 3.11+  
* FastAPI 0.116+  
* SQLAlchemy 2.0 (async)  
* Pydantic v2  
* SQLite + aiosqlite  
* Alembic 1.16+  
* Uvicorn  
* pytest + httpx (для тестов)  

Итоговая структура проекта
--------------------------
movies_api/
├── alembic/                     # миграции
│   ├── versions/
│   └── env.py
├── src/
│   ├── init.py
│   ├── main.py                  # точка входа FastAPI
│   ├── database.py              # AsyncEngine & SessionLocal
│   ├── models/
│   │   ├── init.py
│   │   └── movie.py             # SQLAlchemy-ORM модель
│   ├── routers/
│   │   └── movies.py            # эндпоинты
│   ├── repositories/
│   │   └── movies.py            # бизнес-логика + запросы к БД
│   └── schemas/
│       ├── init.py
│       └── movie.py             # Pydantic-схемы
├── tests/
│   ├── conftest.py              # pytest-фикстуры
│   └── test_movies.py           # тесты
├── alembic.ini
├── requirements.txt
└── README.md
