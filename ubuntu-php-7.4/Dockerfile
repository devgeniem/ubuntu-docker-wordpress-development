FROM devgeniem/ubuntu-docker-wordpress:php74-stable
MAINTAINER Ville Pietarinen - Geniem Oy <ville.pietarinen-nospam@geniem.com>

ENV \
    # Display errors for easier debugging
    PHP_DISPLAY_ERRORS="on" \
    # You can change this env to allow profiling or debugging your application with Xdebug.
    # This is disabled by default because it adds plenty of overhead when it's not needed.
    # Default: off
    XDEBUG_MODE=off \
    XDEBUG_IDE_KEY=DEBUG \
    # Directory to store Xdebug profiling data
    XDEBUG_OUTPUT_DIR="/tmp/xdebug" \
    # Use OSX IP address loopback hack: https://gist.githubusercontent.com/ralphschindler/535dc5916ccbd06f53c1b0ee5a868c93/raw/com.ralphschindler.docker_10254_alias.plist
    # This can be overridden by you
    XDEBUG_CLIENT_HOST="10.254.254.254" \
    # This is the default recommended port.
    XDEBUG_CLIENT_PORT="9003" \
    # Log to container's STDOUT.
    XDEBUG_LOG=/dev/stdout \
    # https://xdebug.org/docs/all_settings#start_with_request
    XDEBUG_START_WITH_REQUEST=yes \
    # https://xdebug.org/docs/all_settings#discover_client_host
    XDEBUG_DISCOVER_CLIENT_HOST=true

# Install xdebug
RUN \

    # Install package from official repo
    apt-get update \
    && pecl install xdebug \
    

    # Create folder for xdebug profiler
    && mkdir -p $XDEBUG_OUTPUT_DIR \

    # Remove custom error pages because they make debugging harder
    && echo "# Disabled" > /etc/nginx/error_pages.conf \

    # enable xdebug
    && printf "\nzend_extension = xdebug.so\n" >> /etc/php/7.4/fpm/php.ini \
    && printf "\nzend_extension = xdebug.so\n" >> /etc/php/7.4/cli/php.ini \

    # Cleanup
    && apt-get clean \
    && apt-get -y autoremove \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /usr/share/doc/* /var/log/apt/*

# Copy our development changes
COPY etc/ /etc/
