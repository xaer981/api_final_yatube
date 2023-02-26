# YaTubeAPI
## Описание

YaTubeApi позволяет создавать посты, писать комментарии к постам, подписываться на любимых авторов. API работает через JWT-токены, однако доступ к чтению постов и комментариев к ним предоставлен любому желающему.

## Установка

Для начала склонируйте репозиторий к себе на машину:

```bash
git clone https://github.com/xaer981/api_final_yatube.git
```


```bash
cd api_final_yatube
```

Затем создайте виртуальное окружение и установите зависимости:

```bash
python -m venv venv
```

```bash
source venv/Scripts/activate
```

```bash
pip install -r requirements.txt
```

После этого необходимо выполнить миграции и можно запускать проект:

```bash
cd yatube_api/
```

```bash
python manage.py makemigrations
python manage.py migrate
```

```bash
python manage.py runserver
```

## Примеры запросов:
1.  ```
    POST http://127.0.0.1:8000/api/v1/jwt/create/
    ```
    В body запроса необходимо указать:
    ```json
    {
        "username": "username",
        "password": "password"
    }
    ```
    
    В ответ вернётся токен для авторизации (access) и для обновления токена (refresh) в случае утери основного.

2.  ```
    GET http://127.0.0.1:8000/api/v1/posts/
    ```
    
    В ответ вернётся список постов.
    
3.  ```
    POST http://127.0.0.1:8000/api/v1/posts/
    ```
    В body запроса необходимо указать:
    ```json
    {
        "text": "" *обязательное поле
        "group": "",
        "image": ""
    }
    ```

#### Полный список запросов и примеры ответов на них можно найти тут:
http://127.0.0.1:8000/redoc/