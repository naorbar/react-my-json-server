# This is an example on how to create a fake local server for development purposes, based on json-server project: 
More info about  json-server project can be found here:

https://my-json-server.typicode.com/</BR>
https://github.com/typicode/json-server

## To create a fake server: 
- `npm install -g json-server` 
	it will install the dependencies to a global folder, 
	e.g.
	`C:\Users\username\AppData\Roaming\npm\node_modules\`
- Create a local folder, e.g. `C:\temp\my-json-server`
- Create a `db.json` file in the given folder:
```
{
  "posts": [
    {
      "id": 1,
      "title": "json-server",
      "author": "typicode"
    }
  ],
  "comments": [
    {
      "id": 1,
      "body": "some comment",
      "postId": 1
    }
  ],
  "profile": {
    "name": "typicode"
  },
  "users": [
	{
		"id": "1",
		"name": "Naor Bar",
		"title": "R&D Team Leader"
	},
	{
		"id": "2",
		"name": "John Doe",
		"title": "VP R&D"
	},
		{
		"id": "3",
		"name": "Jane Doe",
		"title": "CEO"
	}
  ],
  "roles": [
	{
		"role_name": "READ"
	},
	{
		"role_name": "WRITE"
	},
	{
		"role_name": "ADMIN"
	}
  ]
}
```	
	
- `cd` to the server's folder
- `json-server --watch db.json` to start the server - it will load the given db.json file and print the supported urls
- Browse to the server on: `http://localhost:3000/`	
	
	e.g.
	```
	http://localhost:3000/posts
	http://localhost:3000/users
	```
- To start the server on a different port use: `json-server --watch db.json -p <port>`

	e.g.
	
	`json-server --watch db.json -p 3001`

## Sample requests:

#### Request: GET
`http://localhost:3001/roles?role_name=READ`
#### Response:
```
[
  {
	"role_name": "READ"
  }
]
```	
## More info:	
- You can use GET, POST, PUT, PATCH or DELETE requests > changes will be automatically and safely saved to db.json
- Your request body JSON should be object enclosed, just like the GET output. (for example {"name": "Foobar"})
- The POST, PUT or PATCH request should include a Content-Type: application/json header to use the JSON in the request body. 
  Otherwise it will result in a 200 OK but without changes being made to the data.	
