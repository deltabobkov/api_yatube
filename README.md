# Проект CRUD для Yatube

![Python](https://img.shields.io/badge/Python-313131?style=flat&logo=Python&logoColor=white&labelColor=306998)
![Django](https://img.shields.io/badge/Django-313131?style=flat&logo=django&labelColor=092e20)
![DjangoREST](https://img.shields.io/badge/Django-REST-313131?style=flat&logo=django&logoColor=white&color=ff1709&labelColor=313131)
![SQLite](https://img.shields.io/badge/SQLite-313131?style=flat&logo=sqlite&logoColor=ffffff&labelColor=033b55)
![Postman](https://img.shields.io/badge/Postman-313131?style=flat&logo=postman&logoColor=ffffff&labelColor=EF5B25)
![Visual Studio](https://img.shields.io/badge/VS%20Code-313131?style=flat&logo=visualstudiocode&logoColor=ffffff&labelColor=0098FF)

## Проект выполнен с целью реализовать API для всех моделей приложения posts.

### Как запустить проект:
1. Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/deltabobkov/api_yatube.git

cd api_yatube
```

2. Cоздать и активировать виртуальное окружение:

```
python -m venv venv

source venv/Scripts/activate
```

3. Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip

pip install -r requirements.txt
```

4. Выполнить миграции:

```
python manage.py migrate
```

5. Создать супер пользователя:

```
python manage.py createsuperuser
```

6. Запустить проект:

```
python manage.py runserver
```

**Проект будет доступен по адресу:**  
http://localhost/

## Примеры API запросов:
<details>
<summary>Пример POST-запроса с токеном Антона Чехова: добавление нового поста:</summary>  
  
```
.../api/posts/
Payload:
{
    "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
    "group": 1
}
```
Пример ответа:
```
{
    "id": 14,
    "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
    "author": "anton",
    "image": null,
    "group": 1,
    "pub_date": "2021-06-01T08:47:11.084589Z"
} 
```
</details>

<details>
<summary>Пример POST-запроса с токеном Антона Чехова: отправляем новый комментарий к посту с id=14:</summary>  
  
```
.../api/posts/14/comments/
Payload:
{
    "text": "тест тест"
} 
```
Пример ответа:
```
{
    "id": 4,
    "author": "anton",
    "post": 14,
    "text": "тест тест",
    "created": "2021-06-01T10:14:51.388932Z"
} 
```
</details>

<details>
<summary>Пример GET-запроса с токеном Антона Чехова: получаем информацию о группе:</summary>  
  
```  
.../api/groups/2/
```
Пример ответа:
```
{
    "id": 2,
    "title": "Математика",
    "slug": "math",
    "description": "Посты на тему математики"
}
```
</details>

