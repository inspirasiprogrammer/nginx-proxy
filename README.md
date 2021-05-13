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
3. Your CA certificate and self-signed SSL certificate will be generated under ```certs``` directory.

## License
[MIT](https://choosealicense.com/licenses/mit/)
