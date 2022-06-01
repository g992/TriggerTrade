# API

`GET` /triggers/getTriggers - возвращает сохраненные триггеры (из конфига)

GET /triggers/getActiveTriggers - возвращает активные триггеры

`POST` /triggers/addTrigger - добавление триггера по конфигу, в теле запроса обьект {trigger: имя триггера, config: конфигурация}

`POST` /triggers/startTrigger - запуск триггера, в теле запроса обьект {trigger: имя триггера}

`POST` /triggers/pauseTrigger - пауза триггера, в теле запроса обьект {trigger: имя триггера}

`POST` /triggers/deleteTrigger - удаление триггера, необходимо что бы он был на паузе и не было активных трейдеров,  в теле запроса обьект {trigger: имя триггера}

POST /triggers/editTrigger - редактирование триггера, в теле {trigger: triggerName, edit: \[{key: key1, value: value1},{key: key2, value: value2}]}

`POST` /triggers/resumeTrigger - возобновление работы триггера, в теле запроса обьект {trigger: имя триггера}

GET /traders/getTraders - возвращает сохраненных трейдеров (из конфига)

POST /traders/addTrader - добавление трейдела в конфиг, в теле {trader: {name: traderName, config: {key: value\}}}

POST /traders/getTradersFromTrigger - возвращает активных трейдеров у активного триггера и их состояния, в теле обьект {trigger: имя триггера}, res - {success: true, traders: {\}}

POST /traders/editTrader - редактирование трейдера, в теле {trader: traderName, edit: \[{key: key1, value: value1},{key: key2, value: value2}]}

POST /traders/deleteTrader - удаление трейдера из конфига, в теле {trader: traderName}

POST /traders/terminateTrader - остановка трейдера, позиция остается, убираются ордера, в теле {trigger: triggerName, trader: traderName}

GET /utils/system - Возвращает системную нагрузку

GET /utils/getIndicators - Возвращает обьект индикаторов

POST /utils/getTrades - в теле {query: {query search\}}, возвращает сделки, найденнные по запросу query search

POST /utils/getOrders - в теле {query: {query search\}}, возвращает ордера, найденнные по запросу query search

GET /utils/getSettings - возвращает обьект настроек

POST /utils/editSettings - в теле обьект настроек
