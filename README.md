# Лабораторная работа 6 — регистрация и вход в Django

Учебный проект об аренде торговых помещений позволяет зарегистрироваться, войти и выйти. После входа доступна форма создания статьи. Проверяются заполнение полей, уникальность имени и правильность данных при входе. Пароли хранятся в виде хешей Django.

## Запуск

При установленном Python 3.11 из корня проекта в PowerShell:

```powershell
py -3.11 -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe src/manage.py migrate
.\.venv\Scripts\python.exe src/manage.py loaddata demo
.\.venv\Scripts\python.exe src/manage.py createsuperuser
.\.venv\Scripts\python.exe src/manage.py test articles
.\.venv\Scripts\python.exe src/manage.py runserver
```

Главная страница: `http://127.0.0.1:8000/`. Регистрация: `/register/`, вход: `/login/`, форма статьи: `/article/new/`, панель администратора: `/admin/`. Для новой базы создайте нужные учётные записи самостоятельно. Учебный набор не содержит пользователей. Ключ Django берётся из `DJANGO_SECRET_KEY` или создаётся случайно при локальном запуске.

Представления находятся в `src/articles/views.py`, шаблоны форм — в `src/articles/templates/`. Модели аренды и защита от пересечения сроков сохранены из предыдущей работы и рассчитаны на SQLite.
