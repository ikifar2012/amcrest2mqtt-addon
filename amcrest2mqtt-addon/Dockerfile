ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
# Install Components
RUN apk add --no-cache \
    python3 \
    py3-pip \
    git
RUN git clone -b ikifar https://github.com/ikifar2012/amcrest2mqtt.git
# Copy data for add-on
RUN pip install -r /amcrest2mqtt/requirements.txt
COPY rootfs /
# ARGS
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION
ARG BUILD_ARCH

# Labels
LABEL \
    io.hass.name="amcrest2mqtt" \
    io.hass.description="A Home Assistant addon for amcrest2mqtt" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Matheson Steplock <mathesonsteplock.ca>" \
    org.label-schema.description="A Home Assistant addon for amcrest2mqtt" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="amcrest2mqtt" \
    org.label-schema.schema-version="1.0" \
    org.label-schema.usage="https://github.com/ikifar2012/amcrest2mqtt-addon/blob/main/README.md" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/ikifar2012/amcrest2mqtt-addon/" \
    org.label-schema.vendor="Matheson's Home Assistant Addons"