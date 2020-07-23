# VBlog Hugo Theme

Блоговая тема для  [Hugo Static Site Generator](https://gohugo.io).

## Необходимая конфигурация

Задать автора по-умолчанию:
```
[Author]
  email = "email@domain.com"
```

Инфо обо всех авторах прописывается в файле `data\authors.json` в следующем формате:

```
{
  "email@domain.com": {
    "name": "Name Surname",
    "avatars": {
      "200": "avatar_200.jpg"
    },
    "summary": "About author info",
    "email": "email@domain.com",
    "web": "https://domain.com",
    "phone": "+79991234567",
    "facebook": {
      "username": "UserName",
      "app_id": "",
      "admins": ""
    },
    "instagram": {
      "username": "UserName"
    },
    "twitter": {
      "username": "UserName"
    },
    "telegram": {
      "channel": "ChannelName"
    }
  }
}
```

Параметры:

```
baseurl = "https://domain.com/"
title = "Title Site"
contentdir    = "content"
layoutdir     = "layouts"
publishdir    = "public"
canonifyurls  = true
pygmentsUseClasses = true
pygmentCodeFences = true
paginate = 6
paginatePath = "page"
defaultContentLanguage = "ru"
languageName = "Русский"
theme = "VBlog"

[Params]
  subtitle = "Subtitle site"
  description = "Long description site"
  favicon = "favicon.ico"
  logo = "img/logo.png"
```

Создаем меню:

```
[[menu.main]]
    name = "Блог"
    url = "/"
    weight = 1

[[menu.main]]
    name = "О сайте"
    url = "/about/"
    weight = 2

[[menu.main]]
    name = "Контакты"
    url = "/contacts/"
    weight = 3
```

И необязательные (на желательные) параметры:

```
[Permalinks]
  post = "/:year/:month/:day/:slug/"
  page = "/:slug/"

[taxonomies]
  category = "categories"
  tag = "tags"
```

## Главная страница

Состоит из нескольких блоков.

### Слайдер с закрепленными постами

Отображается до 5 статей с категорией `pinned`.

### Блок рейтингов

Информация берется из файла `data\top.json`. Формат JSON выбран для более легкой 
замены источника данных (например, на вызов API).

Формат данных для рейтинга:
```
[
  {
    "title": "ТОП программ лояльности",
    "top": {
      "1": {
        "title": "Miles & More",
        "url": "https://www.miles-and-more.com/"
      },
      "2": {
        "title": "Flying Blue",
        "url": "https://www.flyingblue.com/"
      },
      "3": {
        "title": "Aeroflot Bonus",
        "url": "https://www.aeroflot.ru/ru-ru/afl_bonus"
      }
    }
  }
]
```

Количество рейтингов не ограничено. Располагаются по 2 в ряд (для широких экранов).
```
[
  {
    ...рейтинг №1
  },
  {
    ...рейтинг №2
  },
  {
    ...рейтинг №3
  }
]
```

###  Блок статей

Постраничный вывод статей в карточках по 3 в ряд (для широких экранов).

## Страница информации о ресурсе

Простая страница с информацией о ресурсе. Обычно располагается по маршруту 
`/about/`. Использует шаблон `page`.


## Страница контактов

Простая страница с информацией о ресурсе. Обычно располагается по маршруту 
`/contacts/`. Использует шаблон `page`.

Содержит контактную информацию и форму обратной связи.