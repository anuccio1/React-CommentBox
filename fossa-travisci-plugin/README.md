# Travis CI plugin for Checking on FOSSA builds.

## Setup

1. You must retrieve a FOSSA API token. This is found in FOSSA under [Account Settings](http://app.fossa.io/account/settings/integrations)
2. You must set this as an environment variable named `FOSSA_API_TOKEN` in your Travis CI build
3. Add a custom build step in your `.travis.yml` file like so: 
	```
		before_script:
			- npm install -g mocha
			- cd fossa-test && npm i && node index.js
	```

4. (optional) Set a timeout for pinging the FOSSA API. By default, timeout is 30 minutes. This can be set via the Environment variable: `FOSSA_POLL_TIMEOUT`. You must specify in milliseconds, ex: `1000 * 60 * 30` (30 minutes)

## Dev

You can set a custom fossa endpoint url as well with Env variable: `FOSSA_ENDPOINT_URL`