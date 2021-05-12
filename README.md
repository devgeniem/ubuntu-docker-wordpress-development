# Docker Wordpress Image for Development
This is development version of our [wordpress docker image](https://github.com/devgeniem/ubuntu-docker-wordpress) with xdebug enabled and opcache disabled.

## Xdebug
For debugging and profiling purposes this container comes with **Xdebug 3**. To enable Xdebug features, change its mode in `XDEBUG_MODE`.
```
XDEBUG_MODE=off # Off by default to optimize performance.
```
For different mode values see: https://xdebug.org/docs/all_settings#mode

If you want to use Xdebug step debugger in your host machine's editor, you can set your Docker host's ip address in `XDEBUG_CLIENT_HOST`.
```
XDEBUG_CLIENT_HOST=10.254.254.254
```

You can also define the IDE session key in `${XDEBUG_IDE_KEY}`. By default it is a generic value: `DEBUG`.
```
XDEBUG_IDE_KEY=DEBUG
```

If profiling features are enabled, tracing, profiling, and garbage collection statistics will be written to a location defined in `XDEBUG_OUTPUT_DIR`.

```
XDEBUG_OUTPUT_DIR=/tmp/xdebug # Default value.
```

For all environment variables for Xdebug, see the [Dockerfile](./Dockerfile)