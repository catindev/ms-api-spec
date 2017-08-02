## Сессии
Хранилище токенов для доступа к остальным эндпоинтам. АПИ для авторизации, аутентификации и вот этого всего.

`POST /sessions`

Body

```{ login, password }```

Response

```{ status: 200, id }```


`GET /sessions/:sessionID`

Response
```{ status: 200, username, type }```

где type = user, admin, partner

Автоматически продлевается при каждом вызове


`DELETE /sessions/:sessionID`

Response

```{ status: 200 }```