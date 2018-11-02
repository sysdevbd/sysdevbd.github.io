API - API Programming Interface
-------------------------------

Browser ----JS-----> Server URL: api.email.com/msg, api.email.com/msg/{id}
        <-----------
            json , yaml, xml (SOAP, XML-rpc), protobuf (grpc.io)

URL/ addr: http://api.email.com

HTTP VERB:

POST
GET
PUT
DELETE
PATCH
--------
OPTIONS
HEAD

Path parameter: http://api.email.com/msg/{id}?k=v&x=y           #j=l
                                              query string      hash string
# just a comment
{
	"to": "acb@email.com",
	"sub": "hello"
	x: {
	  c: d
	}
}
-----------
# just a comment

to: abc@email.com
sub: hello
x:
  c: d


-----------


Response

Status Code: 201 (created)

{
	"id": "*&***************",
	""
}

-----------

Status Code: 501 (internal error)

{
	"error": "*&***************"
}

-------------------------------------

Representational State Transfer
===============================
REST
====

Resource: Item, Items

CRUD   | SQL                          |
--------------------------------------|--------------------------
Create | Insert into items()          | POST  http://api.store.com/items  BODY (new item)
                                              Header:
                                              Content-Type: application/json | application/yaml | application/protobuf MIME
                                               {
                                               		"name": "pencil",
                                               		"count": 5
                                               }
                                               ------------------------------------------
                                               201
                                               {
                                               		"id": 1
                                               }

Read   | Select from Items where id = | GET http://api.store.com/items/{id}
                                            200                             | 404
                                            {
                                               "id": 1,
                                               "name": "pencil",
                                               "count": 5
                                            }

List   | Select from Items            | GET http://api.store.com/items
                                            200
                                            [
                                              {
                                              	id: 1,

                                              },
                                              {
                                                id: 2

                                              }
                                            ]

Update | Update item count=5          | PUT http://localhost:8080/items/{id = 1}
                                        {
                                            "name": "pencil",
                                            "count": 2

                                        }
                                        200 OK
                                            {
                                               "id": 1,
                                               "name": "pencil",
                                               "count": 2
                                            }



                                       PATCH http://api.store.com/items/{id = 1}
                                       [
                                       {
                                        "op": "replace",
                                        "path": "/count",
                                        "value": 2
                                       }
                                       ]

                                       Json PATCH


Delete | Delete from              | DELETE http://api.store.com/items/{id = 1}
									200 OK
                                    {
                                       "id": 1,
                                       "name": "pencil",
                                       "count": 2
                                    }



Browser ------> LB -----> server




type Person struct {
	Name string 
	Age  int    `json:"age"`
}

{
	"Name": "x",

}



AuthZ: Does X has permission?

AuthN: Who is doing this?
--------------------------
Header

Content-Type:
Authorization: <>


Basic AuthN:

Authorization: Basic YWRtaW46ZGVtbw==

base64(username:password)


-----------------
Bearer AuthN:

Authorization: Bearer 45003d0c0339a9688f94bdaea4bf051e59d16644

JWT: Javascript Web Token








