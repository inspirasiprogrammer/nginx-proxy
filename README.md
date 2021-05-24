# nginx-proxy
A docker compose configuration for web development using [nginx-proxy](https://github.com/nginx-proxy/nginx-proxy) and [self signed proxy companion](https://github.com/sebastienheyd/docker-self-signed-proxy-companion).

## Usage

1. Create a docker network named nginx-proxy-network.

```bash
docker network create --driver bridge nginx-proxy-network
```

2. Run the service inside nginx-proxy directory.

```bash
docker compose up -d
```
3. Add ca.crt to your browser so that your upcoming web apps will be trusted. 

4. Run your web server container by adding environment variables VIRTUAL_HOST, VIRTUAL_PORT, and SELF_SIGNED_HOST. This is an example using [laravel-web-dev docker image](https://hub.docker.com/r/dptsi/laravel-web-dev).

```bash
docker run -d \
--name your.domain.com \
-v /path/to/your/web/project:/var/www/html \
-e VIRTUAL_HOST=your.domain.com \
-e VIRTUAL_PORT=8080 \
-e SELF_SIGNED_HOST=your.domain.com \
dptsi/laravel-web-dev
```
4. Your CA certificate and self-signed SSL certificate will be generated under ```certs``` directory.

## License
[MIT](https://choosealicense.com/licenses/mit/)
