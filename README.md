# Docker Wordpress Image for Development
This is development version of our [wordpress docker image](https://github.com/devgeniem/ubuntu-docker-wordpress) with xdebug enabled and opcache disabled.

## Options
If you want to use xdebug trace in your local editor you can set your ip address in `XDEBUG_REMOTE_HOST`.
```
XDEBUG_REMOTE_HOST # Default: '10.254.254.254'
```

This container helps you to profile your site with xdebug but this comes with cost of slower development environment.
```
XDEBUG_ENABLE_PROFILE # Default: 0
```

Set `XDEBUG_ENABLE_PROFILE=1` to enable profiling.
