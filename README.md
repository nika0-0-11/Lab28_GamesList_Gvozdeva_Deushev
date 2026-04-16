# Лабораторная работа №28. Веб-сервер на C#: список любимых игр с полным управлением

---

## Описание проекта

API позволяет:

- Получить список всех игр
- Получить информаицию об игре по ID
- Добавить новую игру
- Обновить данные существующей игры
- Удалить игру из списка
- Получить список избранных игр

Данные храняться в памяти сервера и сбрасываются при перезапуске приложения.

---

## Инструкция по запуску

```bash
cd GamesApi
dotnet watch run
```

---

## Таблица всех маршрутов

|Метод|Маршрут|Описание|Статус|
|:---:|:-----:|:------:|:----:|
|**GET**|/api/games|Получить все игры|200|
|**GET**|/api/games/{id}|Получить игру по id|200 / 404|
|**POST**|/api/games|Добавить игру|201|
|**DELETE**|/api/games/{id}|Удалить игру|204 / 404|

---

## Примеры curl-команд

### GET все игры

```bash
curl http://localhost:5200/api/games
```

### GET игру по ID

```bash
curl http://localhost:5200/api/games/1
```

### GET избрвнные игры

```bash
curl http://localhost:5200/api/games/favourites
```

### POST добавить новую игру

```bash
curl -X POST http://localhost:5200/api/games \
 -H "Content-Type: application/json" \
 -d "{\"title\": \"Stardew Valley\", \"genre\": \"Simulation\", \"releaseYear\":
2016}"
```

### PUT обновить игру 

```bash
curl -X PUT http://localhost:5200/api/games/2 \
 -H "Content-Type: application/json" \
 -d "{\"title\": \"Witcher 2: Assassins of Kings\", \"genre\": \"Action RPG\",
\"releaseYear\": 2011}"
```

### DELETE удалить игру

```bash
curl -X DELETE http://localhost:5200/api/games/1
```

### Просмотр статус-кода ответа

```bash
curl -i http://localhost:5200/api/games/812
```