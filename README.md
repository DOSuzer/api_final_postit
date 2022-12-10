### Описание
Данный проект предоставляет доступ к сервису Yatube посредством API.
### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/DOSuzer/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
py -3.7 -m venv env
```

```
. venv/Scripts/activate
```

Установить зависимости из файла requirements.txt:

```
python -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```
### Примеры взаимодействия:
Вам доступны такие эндпойнты:
- api/v1/posts/ - список всех постов
- api/v1/groups/ - список всех групп
- api/v1/posts/<post_id>/comments/ - список всех комментариев к посту, здесь и далее <post_id> это номер поста
- api/v1/follow/ - список всех подписок (только для авторизованного пользователя)
Пример публикации поста (POST запрос к api/v1/posts/):
```
{
    "text":"Мой первый пост!"
}
```
Пример редактирования поста (PATCH запрос к api/v1/posts/<post_id>/):
```
{
    "text":"Новый текст!",
    "group":3
}
```
Пример добавления комментария (POST запрос к api/v1/posts/<post_id>/comments/):
```
{
    "text":"Пост интересный. Спасибо!!"
}
```
Пример подписки на автора (POST запрос к api/v1/follow/):
```
{
    "following":"user1"
}
```