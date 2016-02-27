---
layout: default
title: Метод Newsfeed.Search
permalink: newsfeed/search/
comments: true
---
# Метод Newsfeed.Search
Возвращает результаты поиска по статусам. Новости возвращаются в порядке от более новых к более старым.

Страница документации ВКонтакте [newsfeed.search](https://vk.com/dev/newsfeed.search).
## Синтаксис
``` csharp
public ReadOnlyCollection<NewsSearchResult> Search(NewsFeedSearchParams @params)
```

## Параметры
Класс **`NewsfeedSearchParams`** содержит следующие свойства:

+ **Query** - Поисковой запрос, например, "New Year". строка
+ **Extended** - Указывается 1, если необходимо получить информацию о пользователе или группе, разместившей запись. По умолчанию 0. флаг, может принимать значения 1 или 0
+ **Count** - Указывает, какое максимальное число записей следует возвращать. Обратите внимание — даже при использовании параметра offset для получения информации доступны только первые 1000 результатов. 
 положительное число, по умолчанию 30, максимальное значение 200
+ **Latitude** - Географическая широта точки, в радиусе от которой необходимо производить поиск, заданная в градусах (от -90 до 90). дробное число
+ **Longitude** - Географическая долгота точки, в радиусе от которой необходимо производить поиск, заданная в градусах (от -180 до 180). дробное число
+ **StartTime** - Время в формате unixtime, начиная с которого следует получить новости для текущего пользователя. Если параметр не задан, то он считается равным значению времени, которое было сутки назад. положительное число
+ **EndTime** - Время в формате unixtime, до которого следует получить новости для текущего пользователя. Если параметр не задан, то он считается равным текущему времени. положительное число
+ **StartFrom** - Идентификатор, необходимый для получения следующей страницы результатов. Значение, необходимое для передачи в этом параметре, возвращается в поле ответа next_from. строка, доступен начиная с версии 5.13
+ **Fields** - Список дополнительных полей для профилей и  групп, которые необходимо вернуть. См. описание полей объекта user и описание полей объекта group. 
Обратите внимание, этот параметр учитывается только при extended=1. список слов, разделенных через запятую

## Результат
В случае успеха возвращает общее количество записей и массив объектов, каждый из которых содержит поля: 

+ **id** — локальный идентификатор записи (для конкретного владельца); 
+ **owner_id** — идентификатор владельца стены, на которой размещена запись. Если стена принадлежит сообществу, то данный параметр равен -gid (идентификатор сообщества со знаком минус); 
+ **from_id** —  идентификатор автора записи; 
+ **date** — время публикации записи в формате unixtime; 
+ **text** — текст записи; 
+ **comments** — содержит информацию о количестве комментариев к записи. Для Desktop-приложений дополнительно содержит следующую информацию: 

## Пример
``` csharp
// Пример кода
```

## Версия Вконтакте API v.5.44
Дата обновления: 28.01.2016 13:09:42