# openwhisk-client-js

JavaScript client library for the [OpenWhisk](https://github.com/openwhisk/openwhisk) platform.
Provides a wrapper around the [OpenWhisk APIs](https://new-console.ng.bluemix.net/apidocs/98#introduction).

## installation

```
$ npm install openwhisk // replace with package name....
```

## usage

```
var openwhisk = require('openwhisk');
var ow = openwhisk('api_key', {namespace: 'default_namespace'});
```

_All operation methods return a Promise resolved asynchronously with the results. Failures are available through the catch method._

```
ow.some_operation().then(function () { // success! }).catch(function (err) { // failed! })
```
### retrieve all actions

```
ow.actions()
```

### invoke an action

```
ow.action('action_name')
```

### invoke an action with options

```
ow.action('action_name', {...})
```

The following options are supported:
- `blocking` - delay returning until action has finished executing (default: `false`)
- `params` - JSON object containing parameters for the action being invoked (default: `{}`)
