Манипуляции с файлами на сервере осуществляются с помощью WebDAV, например, таким образом (из командной строки):
````bash
$ curl -X PUT -T leather.pcm --user login:password https://runapi.megafon.ru/media/prompts/leather.pcm
$ curl -X GET -H --user login:password https://runapi.megafon.ru/media/records/b8970e12-5a3e-422d-9301-16f9587343c3-3.pcm
````
Аналогичные операции можно совершать из программного кода, например, на Питоне это могло бы быть организовано вот так:
````python
import requests
records_url = "https://runapi.megafon.ru/media/records/"
r = requests.get(records_url+fname,headers={'Authorization':'Bearer '+apiKey})
open(fname,'wb').write(r.content)
````
