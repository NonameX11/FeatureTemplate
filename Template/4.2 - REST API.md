# REST API

Справка - Что такое REST API и его методы вызовов:

> Подробная обучающая статься https://systems.education/what-is-rest
>  Больше о REST API
	https://yandex.cloud/ru/docs/glossary/rest-api
	https://www.smashingmagazine.com/2018/01/understanding-using-rest-api/     

## Основные типы API и REST среди них

![main api types](https://github.com/user-attachments/assets/aa80233d-2e2c-42e8-a264-1e0cae657a03)
	
## **REST** (**Re**presentational **S**tate **T**ransfer) — архитектурный стиль для передачи репрезентативного состояния.

Описывает, как спроектировать интерфейс взаимодействия одного приложения с другими по протоколу HTTP(S), в формате "Клиент-сервер".
Главная особенность REST API — обмен сообщениями без сохранения состояния. Каждое сообщение самодостаточное и содержит всю информацию, необходимую для его обработки.
Позволяет передавать различные форматы сообщений - JSON (Наиболее часто встречающийся в WEB), XML, HTTP, URL.
Предусматривает обеспечение CRUD - Операций

<details>
  <summary> Что такое CRUD </summary
				   
CRUD — это аббревиатура, обозначающая четыре основных операции управления данными: create, read, update, delete/destroy, то есть создание, чтение, обновление и удаление. Это действия, которые мы совершаем с любой информацией, в любых системах: на сайтах, в приложениях, базах данных. 

</details>

### Структура REST - взаимодействия


## Принципы REST:

1. **Клиент-серверная архитектура.**
	Разделение некоторых зон ответственности: в разделении функций клиента и сервера.
	Клиент реализует только функциональное взаимодействие с сервером. 
	Сервер реализует в себе логику хранения данных, сложные взаимодействия со смежными системами.
	
2. **Stateless**
	Cервер не должен хранить у себя информацию о сессии с клиентом.
	Он должен в каждом запросе получать всю информацию для обработки.

4. **Кэширование**
	Каждый ответ сервера должен иметь пометку, можно ли его кэшировать
		
5. **Единообразие интерфейса - Hypermedia as the Engine of Application State (HATEOAS)**
	 Сервер возвращает не только ресурс, но и его связи с другими ресурсами и действия, которые можно с ним совершить.
	
6. **Layered system  (слоистая архитектура)**
	Ни клиент, ни сервер не должны знать о том, как происходит цепочка вызовов дальше своих прямых соседей.
	
7. **Code on demand  (код по требованию)**
	Идея передачи некоторого исполняемого кода (или программы) от сервера клиенту. 
	
== Подробнее: ==

> https://ninenines.eu/docs/en/cowboy/2.12/guide/rest_principles/         
> https://systems.education/what-is-rest


### Список методов  - ДОБАВИТЬ PATCH и УРЛЫ https://www.ibm.com/docs/en/netcoolomnibus/8.1?topic=interface-http-uris

Описание назначения и состава REST методов.

> Все примеры запросов и ответов взяты отсюда: https://www.ibm.com/docs/en/netcoolomnibus/8.1?topic=examples-table-collection-get-request

#### GET 

Метод для получения информации об объекте (ресурсе).
Удобен  и одновременно ограничем тем, что все данные запрашиваются в header запроса.
(+) МОЖНО
Запрашивать содержимое страниц каталогов, магазинов, WEB UI
(-) НЕ НУЖНО
Передавать конфиденциальные данные, логины+пароли и т.п.

> Подробное описание:  https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET | 


<details>
  <summary> Запрос </summary
			  
  
```
GET /objectserver/restapi/alerts/status HTTP/1.1
Accept: application/json
Authorization: Basic dGVzdHVzZXIwMTpuZXRjb29s
Host: localhost
Connection: keep-alive
```

</details>


<details>
  <summary> Ответ  </summary
			  
  
```
HTTP/1.1 200 OK
Cache-Control: no-cache
Server: libnhttpd
Date: Wed Jul 4 15:32:03 2012
Connection: Keep-Alive:
Content-Type: application/rdf+xml
Content-Length: 24860
	{
"rowset":	{
		"osname":	"NCOMS",
		"dbname":	"alerts",
		"tblname":	"status",
		"coldesc":	[{
				"name":	"Identifier",
				"type":	"string",
				"size":	255
			}, {
				"name": "Serial",
				"type": "integer",
				"size": 4
			}, {
				"name": "Node",
				"type": "string",
				"size": 64
			}, {
				"name": "NodeAlias",
				"type": "string",
				"size": 64
			}, {
				"name": "AlertKey",
				"type": "string",
				"size": 255
			}, {
				"name": "Severity",
				"type": "integer",
				"size": 4
			}, {
				"name": "Summary",
				"type": "string",
				"size": 255
			}, {
				"name": "StateChange",
				"type": "utc",
				"size": 4
			}, {
				"name": "FirstOccurrence",
				"type": "utc",
				"size": 4
			}, {
				"name": "LastOccurrence",
				"type": "utc",
				"size": 4
			}, {
				"name": "RowSerial",
				"type": "integer",
				"size": 4
			}],
		"rows":		[{
				"Identifier": "Startup@sol9-build1",
				"Serial": 12469,
				"Node": "sol9-build1",
				"NodeAlias": "",
				"AlertKey": "",
				"Severity": 0,
				"Summary": "ObjectServer NCOMS on sol9-build1 started at Wed Jul 04 15:27:57 2012",
				"StateChange": 1341412082,
				"FirstOccurrence": 1341411978,
				"LastOccurrence": 1341412077,
				"RowSerial": 12469
			}, {
				"Identifier": "ProfilerEnableToggle@NCOMS:sol9-build1",
				"Serial": 12468,
				"Node": "sol9-build1",
				"NodeAlias": "",
				"AlertKey": "",
				"Severity": 0,
				"Summary": "ObjectServer NCOMS Profiler enabled at Wed Jul 04 15:27:56 2012",
				"StateChange": 1341412077,
				"FirstOccurrence": 1341411976,
				"LastOccurrence": 1341412076,
				"RowSerial": 12468
			}, {
				"Identifier": "JUnitEventTestInstance####0",
				"Serial": 12469,
				"Node": "sol9-build1",
				"NodeAlias": "",
				"AlertKey": "JUnitEventInstance",
				"Severity": 0,
				"Summary": "This is a test event generated by the JUnit REST Event Tests. (0)",
				"StateChange": 1341412184,
				"FirstOccurrence": 1341411772,
				"LastOccurrence": 1341412074,
				"RowSerial": 12468
			}, {
				"Identifier": "Shutdown@sol9-build1",
******* TRUNCATED ********
				"RowSerial": 12519
			}],
		"affectedRows": 12
	}
}
```

</details>

#### POST

Метод для создания нового объекта (ресурса) 

> Подробное описание:  https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST


<details>
  <summary> Запрос </summary
			    
```
Accept: application/json
Authorization: Basic dGVzdHVzZXIwMTpuZXRjb29s
Content-Type: application/json
Host: localhost
Connection: keep-alive
Content-Length: 984

{
	"rowset":	{
			"coldesc": [ {
					"type": "string",
					"name": "Identifier"
			}, {
					"type": "string",
					"name": "Node"
			}, {
					"type": "string",
					"name": "AlertKey"
			}, {
					"type": "integer",
					"name": "Severity"
			}, {
					"type": "string",
					"name": "Summary"
			}, {
					"type": "utc",
					"name": "FirstOccurrence"
			}, {
					"type": "utc",
					"name": "LastOccurrence"
			}, {
					"type": "integer",
					"name": "OwnerUID"
			}, {
					"type": "integer",
					"name": "OwnerGID"
			}],
			"rows":	[ {
					"FirstOccurrence": 1341412087,
					"Node": "localhost",
					"AlertKey": "JUnitEventInstance",
					"Summary": "This is a test event generated by the JUnit REST Event Tests.(1)",
					"LastOccurrence": 1341412087,
					"Identifier": "JunitEventTestInstance####1",
					"OwnerGID": 0,
					"Severity": 4,
					"OwnerUID": 0
		}]
	}
}
```

</details>


<details>
  <summary> Ответ  </summary
			  
  
```
HTTP/1.1 201 Created
Location: http://localhost/objectserver/restapi/alerts/status/kf/12481%3ANCOMS
Cache-Control: no-cache
Server: libnhttpd
Date: Wed Jul 4 15:31:53 2012
Connection: Keep-Alive
Content-Type: application/json;charset=UTF-8
Content-Length: 304
{
	"entry":	{
		"affectedRows": 1,
		"keyField": "12481%3ANCOMS",
		"uri": "http://localhost/objectserver/restapi/alerts/status/kf/12481%3ANCOMS"
	}
}
```

</details>


#### PUT

Метод для полной замены объекта (ресурса) на обновленную версию 

> Подробное описание:  https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT

Пример структуры:

<details>
  <summary>Запрос </summary
			  
  
```

```

</details>

<details>
  <summary> Ответ </summary
			  
  
```

```

</details>

#### PATCH

Метод для частичного изменения объекта (ресурса) 

> Подробное описание: https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH


<details>
  <summary>Запрос </summary
			  
  
```
PATCH /objectserver/restapi/alerts/status HTTP/1.1
Accept: application/json
Authorization: Basic dGVzdHVzZXIwMTpuZXRjb29s
Content-Type: application/json
Host: localhost
Connection: keep-alive
Content-Length: 1092
{
	"rowset": {
		"coldesc": [
			{
				"type": "integer",
				"name": "Acknowledged"
			},
			{
				"type": "string",
				"name": "Location"
			},
			{
				"type": "integer",
				"name": "OwnerUID"
			},
			{
				"type": "integer",
				"name": "OwnerGID"
			},
			{
				"type": "utc",
				"name": "LastOccurrence"
			}
		],
		"rows": [
			{
				"Location": "UPDATED",
				"LastOccurrence": 1341412235,
				"Acknowledged": 1,
				"OwnerUID": 65534,
				"OwnerGID": 1
			}
		]
	}
}
```

</details>



<details>
  <summary> Ответ  </summary
			  
  
```
HTTP/1.1 200 OK
Cache-Control: no-cache
Server: libnhttpd
Date: Wed Jul 4 15:32:03 2012
Connection: Keep-Alive:
Content-Type: application/json;charset=UTF-8
Content-Length: 158
{
	"entry":	{
		"affectedRows": 10,
		"uri": "http://localhost/objectserver/restapi/alerts/status"
	}
}
```

</details>

#### DELETE

Метод для удаления информации об объекте (ресурсе) 

> Подробное описание: https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE

<details>
  <summary>Запрос </summary
			  
  
```
DELETE /objectserver/restapi/alerts/status HTTP/1.1
Accept: application/json
Authorization: Basic dGVzdHVzZXIwMTpuZXRjb29s
Host: localhost
Connection: keep-alive
```

</details>


<details>
  <summary> Ответ  </summary
			  
  
```
HTTP/1.1 200 OK
Cache-Control: no-cache
Server: libnhttpd
Date: Wed Jul 4 15:38:53 2012
Connection: Keep-Alive:
Content-Type: application/json;charset=UTF-8
Content-Length: 157
{
	"entry":	{
		"affectedRows": 10,
		"uri": "http://localhost/objectserver/restapi/alerts/status"
	}
}
```

</details>

### Подробнее о Структуре  REST вызова

Вызов состоит из запроса и ответа.

### Структура запроса в REST вызове

#### Схема на примере метода POST

* Запрос:

![структура запроса](https://github.com/user-attachments/assets/643412d6-ef96-469a-b58b-08e2066ff388)

* Ответ:

![структура ответа](https://github.com/user-attachments/assets/dedc2d09-b6cd-4e8f-9184-7e9b509ceb70)


#### Описание

1. Method:
	GET, POST и т.д.
	> Подробнее: см. таблицу выше

3. Header
	Cодержит атрибуты сообщения, например: информация о безопасности, типе контента или о сетевой маршрутизации.
	> Подробнее: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers

4. Body
	Тело запроса
	Непосредственно, содержимое запроса.
	JSON, XML, HTTP, URL Контент

### Структура ответа в REST вызове

1. Status Code
	Содержит HTTP Код ответа, означающий результат запроса
	200, 400, 500
	> Подробнее: https://developer.mozilla.org/en-US/docs/Web/HTTP/Status

2. Header
	Cодержит атрибуты сообщения, например: информация о безопасности, типе контента или о сетевой маршрутизации.
	> Подробнее: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers

3. Body
	Непосредственно, содержимое ответа.
	JSON, XML, HTTP, URL Контент   
	

## Структура сообщения вызова REST

![rest_request](https://github.com/user-attachments/assets/94893027-7033-4a47-95db-08b1c79a2d1b)

