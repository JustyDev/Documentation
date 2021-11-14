---
description: Позволяет получить список серверов с минимальной информации о них
---

# Servers.Get

{% hint style="success" %}
Публичный метод. Вы можете использовать этот метод без аутентификации приложения.
{% endhint %}

{% swagger method="get" path="/servers.get" baseUrl="https://api.elician.ru" summary="Получение информации о всех серверах проекта" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-response status="200: OK" description="Ответ сервера в случае успешного выполнения:" %}
```javascript
{
    "body": {
        "servers": [
            {
                "id": 1,//Идентификатор сервера в нашей системе.
                "info": {
                    "name": "Eldritch Magic",
                    "version": "1.12.2"
                    "type": "Magic",
                    "desc": "Eldritch Magic - магия в вас",
                    "items": 13,
                    "tag": ["VIPED", "#46b2fa"] //См. ServerTags
                },
                "world": {
                    "size" => "10000x10000",
                    "vipe" => "13 октября 2021",
                    "php" => "PvPvE"
                },
                "online": {
                    "max": 100,
                    "now": 47,
                    "status": "online",
                    "players": [//Полный список игроков в сети прямо сейчас
                        "Justy", "MrFoxHD"
                    ]
                },
                "testMode": 0, //См. Общее тестирование
            }
        ],
        "online": [
            "max": 1500,
            "now": 100,
            "record": [//записи максимального онлайна за всё время
                "max": 760,
                "date": "15 января 2020",
                "servers": [//онлайн каждого сервера на период "date"
                    {
                        "server": "Factory",
                        "online": 97
                    },
                    {
                        "server": "Dizarray",
                        "online": 13
                    }
                ]
            ]
        ]
    }
}
```
{% endswagger-response %}
{% endswagger %}

### ServerTags

Объект тегов серверов содержит теги сервера, которые присваиваются в зависимости от некоторых периодов

#### Возможные значения

* `["TODAY", "#f5222d"`] - открытие сервера сегодня
* `["SOON", "#fa8c16"`] - открытие сервера скоро
* `["NEW", "#76c148"`] - новый сервер (если открыт менее недели назад)
* `["VIPED", "#46b2fa"`] - очищенный (если был вайпнут менее недели назад)
* `["UPPED", "#fa8c16"`] - обновлённый (если был обновлён менее недели назад)

