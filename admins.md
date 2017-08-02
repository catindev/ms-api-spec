# Администраторы
Супер-пользователи и партнёры


### POST /admins
Body
```
{ session, name, password, type, [accounts] }
```
Response
```
{ status: 200, id }
```


### GET /admins/?session
Или для конкретного пользователя `GET /admins/:adminID?session`

Опционально в querystring: 
- [id] - массив идентификаторов (игнорируется если задан adminID)
- search - строка запроса на поиск по имени (если задан параметр id, то игнорируется)
- type - конкретного типа

response 
```
{ 
    status: 200, 
    items: [
        { id, username, type }
    ]
}
```


### PUT /admins/:adminID
Body
```
{ session }
```
Опционально в body: name, password, type, [accounts]

Response
```
{ status: 200 }
```
Если вызывает не админ, то возвращает ошибку: 
```
{ 
    status: 400, 
    message: "У этого пользователя нет доступа к управлению администраторами" 
}
```


### DELETE /admins/:adminID?session
Response
```
{ status: 200 }
```
Если вызывает не админ, то возвращает ошибку: 
```
{ 
    status: 400, 
    message: "У этого пользователя нет доступа к управлению администраторами" 
}
```