Нет. Это означает, что вы в своём коде открываете WebSocket на точку включения (endpoint). Например, в примерах на Питоне это может выглядить как-то так
````python
import asyncio
from jsonrpc_websocket import Server,ProtocolError
endpoint_url = "wss://runapi.megafon.ru/v1/api/"
megafon = Server(endpoint_url+apiKey)
await megafon.ws_connect()
````
Как только ws-сессия будет успешно открыта, входящий трафик автоматически маршрутизируется на ваше приложение.
