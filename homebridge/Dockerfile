FROM homebridge/homebridge:latest

RUN apt-get update \
    && apt-get install -y --no-install-recommends nginx \
    && rm -f /etc/nginx/sites-enabled/default /etc/nginx/conf.d/default.conf \
    && mkdir -p /run/nginx \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY rootfs /
