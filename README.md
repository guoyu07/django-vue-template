## Quick Start

1. Build frontend

```shell
npm install
npm run build
```

 When you are developing, run 

```shell
npm run watch
```

to compile your frontend code dynamically.



2. Configure MySQL

 Change ```settings.py``` :

```python
DATABASES = {
    'default': {
        ...
        'NAME': 'your database name',
        'USER': 'database user name'.
        'PASSWORD': 'your password',
        ...
    }
}
```

 Enter MySQL, create your database:

```mysql
create database database-name default character set utf8 collate utf8_unicode_ci;
```



3. Run django

 Before that, configure your database:

```shell
python manage.py makemigrations
python manage.py migrate
```

Then run django by:

```shell
python manage.py runserver 8000
```

Use python3 when ```python``` doesn't work, depending on your python version (python2 or python3), or you can run a  virtual environment.



4. Visit your site

 Visit your site by ```localhost:8000```.



5. Deploy on server

Replace the configure file of nginx ( mine is ```/etc/nginx/nginx.conf``` ) with file in project.

Run command:

```shell
uwsgi --ini uwsgi/uwsgi-conf.ini
sudo service nginx start
```

