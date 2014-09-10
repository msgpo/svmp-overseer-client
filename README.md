# Client API for SVMP Overseer

## Install
 
```npm install```

## Quick Start

```javascript
  var client = require('svmp-overseer-client');
  
  // URL of the Overseer host and an svmp token with admin privs
  var api = new client('URL','SVMPTOKEN');
  
  api.listUsers(function(err, result) {
      if(err) {
         console.log("Got an Error!", err);
      } else {
         console.log("Got: ", result.body);
      }
  });
```

Each API requires at least a callback function in the form:

```javascript
  function(err, result) {} ;
```

Where 'result' is the response object.  You can access the information like any other response object:
'result.statusCode', 'result.body' etc...

## API

```listUsers(callback)```

List all Users in the system

```createUser(username, password, email, device_type, callback)```

Add a new User

```deleteUser(username, callback)```

Delete a User

```getUser(username, callback)```

Get a User

```updateUser(username, updates, callback)```

Update a given user (by username). ```updates``` is object with the fields and values to update: ```{email: 'new@here.com'}```


```listDevices(callback)```

List devices know to the system


```listVolumes(callback)```

List all Volumes known by the system


```assignVolume(username, volume_id, callback)```

Assign an existing Volume to a user


```listImages(callback)```

List all VM images


```createVolume(username, callback)```

Create a VM Volume for a given User


```setupVM(username, callback)```

Create and start a VM for a given User













