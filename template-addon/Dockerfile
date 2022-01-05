ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
# Install Components
RUN echo "hi"
# Copy data for add-on
COPY run.sh /
RUN chmod +x run.sh
CMD [ "./run.sh" ]
# ARGS
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION
ARG BUILD_ARCH

# Labels
LABEL \
    io.hass.name="Template" \
    io.hass.description="Template Add-on" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Matheson Steplock <mathesonsteplock.ca>" \
    org.label-schema.description="Template Add-on" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="Template" \
    org.label-schema.schema-version="1.0" \
    org.label-schema.usage="https://github.com/ikifar2012/ha-addon-template/blob/master/README.md" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/ikifar2012/ha-addon-template/" \
    org.label-schema.vendor="Matheson's Home Assistant Addons"