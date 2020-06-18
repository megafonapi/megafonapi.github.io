УРЛ точки входа состоит из базовой строки `runapi.megafon.ru/v1/api/` и API-ключа, сгенерированного на [dev.megafon.ru](http://dev.megafon.ru/). Такая конструкция обусловлена тем, что APIkey нельзя
уложить в `Authorization:` в заголовке при работе с сокетом в JS-коде _из браузера_ (браузеры запрещают). Точку входа и следует передавать функции установки соединения. Поскольку мы работаем через WebSocket, 
то организация SSL-соединения, например на Питоне, выглядит так 
```python
endpoint_url = "wss://runapi.megafon.ru/v1/api"
APIkey = "bacb9d06-1e9f-4740-a877-3f6572376217-738ab080-f041-4e7e-989e-742db0c2a2d3"

megafon = Server(endpoint_url+"/"+APIkey)
```
