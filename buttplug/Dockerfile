ARG BUILD_FROM=ghcr.io/hassio-addons/base:17.2.4
FROM $BUILD_FROM

# Install requirements for add-on
RUN \
  apk add --no-cache \
    nginx \
    nodejs \
    npm

COPY rootfs /

COPY buttplug-test /
RUN cd / && npm install --unsafe-perm

# Labels
LABEL \
    io.hass.name="${BUILD_NAME}" \
    io.hass.description="${BUILD_DESCRIPTION}" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Catqwe"
