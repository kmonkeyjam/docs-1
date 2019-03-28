---
id: js-operations
title: JavaScript operations
---


## Run

`api.run(operation, [parameters={}], [options={}])`

Runs an operation.

| Argument | Type |  |
| :--- | :--- | :--- |
| operation | String | the name of the operation to be run |
| [parameters={}] | Object | an object containing any operation-defined parameters |
| [options={}] | Object | additional options --  `limit`: limits the number of results returned. Infinity if undefined. `asUser`: runs the operation with the credentials provided by the user with this email address. Current user if undefined. |

**Returns** (Array): Returns the operation results or throws any operation failure.

**Examples**

```javascript
api.run("this.helloworld");
// => [{"Hello": "World"}]

api.run("source.users", { id: params.userId });
// => [{id:1234, ...}]

api.run("connection.many_results", {}, {limit: 10});
// => returns result array of size 10

api.run("this.tickets_in_progress", {}, {"asUser": "iggy@transposit.com"})
// => runs the operation with iggy's provided credentials
```

## Run bulk

`api.runBulk(operations)`

Runs any number of operations in parallel and waits for all to complete, or any to fail, before returning.

| Argument | Type |  |
| :--- | :--- | :--- |
| operations | Array<Object> | an array of descriptor objects, each describing one of the operations to run in parallel |

Each descriptor object has the following properties:

| Field | Type |  |
| :--- | :--- | :--- |
| operation | String | the name of the operation to be run |
| [parameters={}] | Object | an object containing any operation-defined parameters |
| [options={}] | Object | additional options - `limit`: limits the number of results returned. Infinity if undefined. |

**Returns** (Array): Returns an array where each element is the result set from one of the parallel operations. If any fail, the error is thrown.

**Example**

```javascript
var results = api.runBulk([{
  operation: "this.helloworld"
}, {
  operation: "source.users",
  parameters: { id: params.userId }
}, {
  operation: "connection.many_results",
  options: { limit: 10 }
}]);

results[0] // => [{"Hello": "World"}]
results[1] // => [{id:1234, ...}]
results[2] // => result array of size 10
```

## Run for all users

`api.runForAllUsers(operation, [parameters={}], [options={}])`

Runs an operation for every production user in parallel.

| Argument | Type |  |
| :--- | :--- | :--- |
| operation | String | the name of the operation to be run |
| \[parameters={}\] | Object | an object containing any operation-defined parameters |
| \[options={}\] | Object | additional options - `limit`: limits the number of results returned. Infinity if undefined. `users`: A list of user emails to run the operation for. If undefined, the operation will be run for all users. |

**Returns** \(Array\): Returns an array where each element is the result set from one of the parallel operations. If any fail, the error is thrown.

**Example**

```javascript
var results = api.runForAllUsers("this.say_hello", {}, {"users": ["iggy@transposit", "support@transposit"]});

results[0] // => [{"greeting": "Hello Iggy!"}]
results[1] // => [{"greeting": "Hello Support!"}]
```

## Query

 `api.query(query, [parameters={}])`

Run a SQL query.

| Argument | Type |  |
| :--- | :--- | :--- |
| query | String | The SQL query to be run |
| [parameters={}] | Object | an object containing any operation-defined parameters |

**Returns** (Array): Returns the query results or throws any query failure.

**Example**

```javascript
api.query("select * from this.helloworld")
// => [{"Hello": "World"}]

api.query("select * from source.users where id=@userId", {userId: params.userId});
// => [{id:1234, ...}]
```

## Get user information

`api.user()`

Get the logged-in user information.

**Returns** (Object): An object that includes the user's `fullName` and `email`

**Example**

```javascript
api.user()
// => {"fullName":"iggy","email":"iggy@transposit.com"}
```

## List users

`api.listUsers()`

**Returns** \(Array\): Returns an array of all logged-in users' `fullName` and `email`. In development, it returns an array containing only the developer running the operation. In production, the array includes all production users.

**Example**

```javascript
api.listUsers()
// => [{"fullName":"iggy","email":"iggy@transposit.com"}, {"fullName":"support","email":"support@transposit.com"}]
```

## Auths

`api.auths(dataConnection)`

Returns credentials for a data connection that uses runtime authentication.

| Argument | Type |  |
| :--- | :--- | :--- |
| dataConnection | String | The name of the data connection to get credentials for |

**Returns** \(Object\): A set of key-value pairs where the key is the credential name and the value is the credential value

**Example**

```javascript
api.auths("myDataConnection");
// => { "mySecret": "REVBREJFRUY="}
```

## Log

`api.log([objects])`

Prints to the debug tab. `console.log()` can also be used.

| Argument | Type |  |
| :--- | :--- | :--- |
| [objects] | String or Object | One or more objects or strings to log. Objects are automatically serialized. |

**Returns** null

**Example**

```javascript
api.log("logging the following greeting:", {"Hello", "World"})
// => logging the following greeting: { Hello: World }
```

## Available JavaScript Libraries

Transposit provides you access to a few different popular JavaScript libraries.

* [qs (v6.5.2)](https://github.com/ljharb/qs)
```javascript
var qs = require('qs.js');
var limited = qs.parse('a=b&c=d', { parameterLimit: 1 });
```

* [underscore](https://underscorejs.org/)
```javascript
var _ = require('underscore.js');
return _.map([1, 2, 3], function(num){ return num * 3; });
```

* [moment](https://momentjs.com/timezone/)
* [moment-timezone](https://momentjs.com/timezone/)
* [moment-timezone-with-data](https://momentjs.com/timezone/)
```javascript
var moment = require('moment-timezone-with-data.js');
var jun = moment("2014-06-01T12:00:00Z");
api.log(jun.clone().tz('America/New_York').format('ha z')); // 8am EDT
```

* [mustache](https://github.com/janl/mustache.js)
```javascript
var mustache = require('mustache.js');
var view = {
  title: "Joe",
  calc: function () {
    return 2 + 4;
  }
};
var output = mustache.render("{{title}} spends {{calc}}", view);
```

* [jsonpath](https://github.com/dchester/jsonpath)

* [cryptoJS](https://cryptojs.gitbook.io/docs/)
```javascript
var CryptoJS = require("crypto-js");

var wordArray = CryptoJS.enc.Utf8.parse(params.text);
var base64 = CryptoJS.enc.Base64.stringify(wordArray);
return base64;
```

