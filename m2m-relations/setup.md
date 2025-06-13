## Инструкция

1. Установка бибилиотек из файла ___requirements.txt___;

```shell
pip install -r requirements.txt
```

2. В папке проекта заходим в файл ___settings.py___ раздел ___INSTALLED_APPS___ и прописываем созданные приложения;

3. В ___settings.py___ в разделе database меняем SQL-lite на postgress:

```sql
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'netology_m2m_relations',
        'HOST': '127.0.0.1',
        'PORT': '5432',
        'USER': 'postgres',
        'PASSWORD': 'postgres',
    }
```

4. Cоздание БД:

```shell
createdb -U postgres netology_m2m_migrations
```

5. Отправка изменений + python manage.py migrate:

```shell
 manage.py makemigrations
```

6. Создание структуры базы данных:

```shell
python3 manage.py migrate
```

7. Загрузка данных в БД:

```shell
python3 manage.py loaddata articles.json
```

8. Создание пользователя для Админ:

```shell
python3 manage.py createsuperuser
```

9. Запуск сервера:

```shell
python3 manage.py runserver
```