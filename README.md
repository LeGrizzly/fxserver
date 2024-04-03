# fxserver

FXServer for FiveM server

## Tags

it's recommended to use `recommended` tag to use recommended FXServer version.

- [`recommended`](https://github.com/xalsie/fxserver/tree/recommended)
- [`optional`](https://github.com/xalsie/fxserver/tree/optional)
- [`latest`](https://github.com/xalsie/fxserver/tree/main)

## Examples

### Docker run

```sh
docker run -it -p 30120:30120/tcp -p 30120:30120/udp \
    -v /yourLocalServerFolder/server.cfg:/opt/cfx-server/server.cfg \
    -v /yourLocalServerFolder/resources:/opt/cfx-server/resources \
    legrizzly/fxserver:recommended +exec server.cfg +set gamename gta5
```

### Docker-compose

```yaml
version: "3.8"

services:
  redm:
    image: legrizzly/fxserver:recommended
    tty: true
    stdin_open: true
    volumes:
      - ./server.cfg:/opt/cfx-server/server.cfg
      - ./resources:/opt/cfx-server/resources
    ports:
      - "30120:30120/tcp"
      - "30120:30120/udp"
    command: +exec server.cfg +set gamename gta5
```

### Image based

```dockerfile
FROM legrizzly/fxserver:recommended

COPY server.cfg server.cfg
COPY resources resources

CMD ["+exec", "server.cfg", "+set", "gamename", "gta5"]
```
