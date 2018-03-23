# Caddyserver
Caddyserver is a high performace, easy to configure webserver written in golang with automatic https configuration through letsencrypt.

This repository contains the Dockerfiles which build the tenforce/caddyserver images.
Due to the fact that the binaries on https://caddyserver.com are not licensed the same way as the source code, the Dockerfiles will build the binaries from source based on an alpine image.

All the binaries produced by the code in this repository is governed by the same license as the underlying caddyserver source code: Apache v2.

The build currently produces a barebones caddyserver without any plugins.
As time progresses and our needs change we will most likely add some tags whith different configurations.

## Usage
In order to use the image, you need to add the website you need to serve and a Caddyfile in `/config`, either by building a new image or using volumes.

The default config file in the base image binds the server to port 80, but does not include any other instructions.

```bash
docker run -p "80:80" -p "443:443" -v "Caddyfile:/config/Caddyfile" -v "build/:/www" tenfoce/caddyserver
```

For more information on how to configure caddy see https://caddyserver.com/docs

## Tags
* *latest*: The latest stable release

## License
Apache v2
