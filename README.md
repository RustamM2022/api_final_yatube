# api_final
api final
## Описание проекта
В этом проекте разработан API для работы с базой данных: 
- создание, редактирование, удаление постов, комментариев к ним
- создание и просмотр пользователей, подписок.

## Установка 
Как запустить проект:
 - Клонировать репозиторий и перейти в него в командной строке:
   
    ```
    git clone git@github.com:ваш-аккаунт-на-гитхабе/api_final_yatube.git
    cd api_final_yatube
    ```

* Cоздать и активировать виртуальное окружение:

   ```
   python -m venv env

   source venv/Scripts/activate
   ```

+ Установить зависимости из файла requirements.txt:

   ```
   pip install -r requirements.txt
   ```

- Выполнить миграции:

   ```
   python manage.py migrate
   ```

* Запустить проект:

   ```
   python manage.py runserver
   ```

## Примеры запросов
- Пример создания подписки: 
    в Postman сначала авторизуемся, используя ранее созданный для текущего пользователя токен, в адресную строку вводим http://127.0.0.1:8000/api/v1/follow/ и далее передаем Post-запрос, в теле которого передаем автора, на которого нужно подписаться
   ```
   {
       "following": "anton"
   }
   ```
- Пример ответа:
   ```
   {
     "user": "rustam",
     "following": "anton"
   }
   ```
- Пример POST-запроса с токеном Антона Чехова: добавление нового поста.
  POST .../api/v1/posts/
   ```
   {
       "text": "Вечером собрались в редакции «Русской мысли», чтобы поговорить о народном театре. Проект Шехтеля всем нравится.",
       "group": 1
   }
   ```
- Пример ответа:
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
## Системные требования
- Python 3.9
- Django 3.2.16
