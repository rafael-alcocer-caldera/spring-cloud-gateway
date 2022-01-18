# SPRING CLOUD GATEWAY EXAMPLE

## Synopsis

The project is a Spring Cloud Gateway. 

## Motivation

I wanted to have some kind of central place to receive all the requests to my services. And from this place be able to route to my services.

## Pre Requirements

- You need to have <https://github.com/rafael-alcocer-caldera/spring-boot-elasticsearch-example>
- You need to have <https://github.com/rafael-alcocer-caldera/spring-boot-kafka-producer-example>

USING POSTMAN:
--------------
<code><pre>
ELASTICSEARCH

GET

http://localhost:9091/elasticsearch/get

Body
----
{"index": "myindex", "id": "1"}

Response:
---------
{
    "fields": {},
    "id": "1",
    "type": "_doc",
    "source": {
        "birthdate": "1950-01-10",
        "hour": "15:30",
        "surname": "TABLE",
        "name": "PETER",
        "age": 56
    },
    "index": "myindex",
    "version": 1,
    "sourceAsString": "{\"name\":\"PETER\",\"surname\":\"TABLE\",\"age\":56,\"birthdate\":\"1950-01-10\",\"hour\":\"15:30\"}",
    "sourceInternal": {
        "fragment": true
    },
    "sourceAsBytesRef": {
        "fragment": true
    },
    "sourceAsMap": {
        "birthdate": "1950-01-10",
        "hour": "15:30",
        "surname": "TABLE",
        "name": "PETER",
        "age": 56
    },
    "seqNo": 0,
    "sourceEmpty": false,
    "primaryTerm": 1,
    "exists": true,
    "sourceAsBytes": "eyJuYW1lIjoiUEVURVIiLCJzdXJuYW1lIjoiVEFCTEUiLCJhZ2UiOjU2LCJiaXJ0aGRhdGUiOiIxOTUwLTAxLTEwIiwiaG91ciI6IjE1OjMwIn0=",
    "fragment": false
}

</code></pre>

KAFKA
POST

http://localhost:9091/kafka/producer

Body
----
{
	"id": "1",
	"topicName": "rac-topic",
	"json": {
		"nombre": "RAFAEL",
		"apellido": "ALCOCER",
		"edad": 1000,
		"fecha": "1900 - 08 - 13"
	}
}

Response:
---------

## License

All work is under Apache 2.0 license