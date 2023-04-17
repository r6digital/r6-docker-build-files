# r6-docker-build-files

This repository contains some config files for Docker projects. It's a drop-in replacement for
the gist we were using previously for this purpose.

Projects created before 2023-04-05 using the Laravel template will have the old URLs in the
`Dockerfile`. These URLs should be replaced, as per the example below. Projects created after
that date are not affected, as they store the config files internally.

**Note: this repository is public.**

## Example

### Before

```dockerfile
FROM base as caddy-up
ARG FPM_CONF_SRC=https://gist.githubusercontent.com/DH-92/bd84c1ac6768f6908d3233f1ae4bbeb1/raw/zz-docker.conf
ARG FPM_CONF_PATH=/usr/local/etc/php-fpm.d/zz-docker.conf
ARG CADDY_SRC=https://gist.githubusercontent.com/DH-92/bd84c1ac6768f6908d3233f1ae4bbeb1/raw/Caddyfile
ARG CADDY_PATH="/etc/caddy/Caddyfile"
```

### After

```dockerfile
FROM base as caddy-up
ARG FPM_CONF_SRC=https://raw.githubusercontent.com/r6digital/r6-docker-build-files/develop/zz-docker.conf
ARG FPM_CONF_PATH=/usr/local/etc/php-fpm.d/zz-docker.conf
ARG CADDY_SRC=https://raw.githubusercontent.com/r6digital/r6-docker-build-files/develop/Caddyfile
ARG CADDY_PATH="/etc/caddy/Caddyfile"
```
