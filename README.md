# CaddyServer Dispatcher
Advantages of the caddyserver implementation are:
* Out of the box websocket proxying
* Easy log format configuration
* 1 line request-id / tracing configuration
* Small docker image

Due to licensing issues, caddy server is compiled from source rather than fetching the precompiled binaries.

## Usage
```bash
docker run -p "80:80" registry.gitlab.com/oslo2/sp-dispatcher:latest
```

## Configuration
A default config file is located in a volume in /config/Caddyfile, just override it with your own configuration.

## TODO
* [] Add a test suite which validates the proxy rules (golang or nodejs are prime candidates because they allow for easy process forking)
