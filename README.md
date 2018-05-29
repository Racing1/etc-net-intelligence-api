Ethereum Classic Network Intelligence API
============
[![Build Status][travis-image]][travis-url] [![dependency status][dep-image]][dep-url]

This is the backend service which runs along with ethereum and tracks the network status, fetches information through JSON-RPC and connects through WebSockets to [etc-netstats](https://github.com/Machete3000/etc-netstats) to feed information. For full install instructions please read the [wiki](https://github.com/Machete3000/etc-net-intelligence-api/wiki/Network-Status-Client-Setup).


## Prerequisite
* ETC node
* npm

## Configuration

Configure the app modifying [processes.json](/etc-net-intelligence-api/blob/master/processes.json). Note that you have to modify the backup processes.json file located in `./bin/processes.json` (to allow you to set your env vars without being rewritten when updating).

```json
"env":
	{
		"NODE_ENV"        : "production", // tell the client we're in production environment
		"RPC_HOST"        : "localhost", // eth JSON-RPC host
		"RPC_PORT"        : "8545", // eth JSON-RPC port
		"LISTENING_PORT"  : "30303", // eth listening port (only used for display)
		"INSTANCE_NAME"   : "", // whatever you wish to name your node
		"CONTACT_DETAILS" : "", // add your contact details here if you wish (email/skype)
		"WS_SERVER"       : 
		"WS_SECRET"       : 
		"VERBOSITY"       : 2 // Set the verbosity (0 = silent, 1 = error, warn, 2 = error, warn, info, success, 3 = all logs)
	}
```

## Run

Run it using pm2:

```bash
cd ~/bin
pm2 start processes.json
```

[travis-image]: https://travis-ci.org/Machete3000/etc-net-intelligence-api.svg
[travis-url]: https://travis-ci.org/Machete3000/etc-net-intelligence-api
[dep-image]: https://david-dm.org/Machete3000/etc-net-intelligence-api.svg
[dep-url]: https://david-dm.org/Machete3000/etc-net-intelligence-api
