# Сессии
Хранилище токенов для доступа к остальным эндпоинтам. АПИ для авторизации, аутентификации и вот этого всего.

### POST /sessions
Body
```
{ login, password }
```
Response
```
{ status: 200, id }
```
Срок действия - 1 неделя.

### GET /sessions/:sessionID
Response
```
{ status: 200, username, type }
```
Где type = user, admin, partner. Автоматически продлевается при каждом вызове

### DELETE /sessions/:sessionID
Response
```
{ status: 200 }
```
