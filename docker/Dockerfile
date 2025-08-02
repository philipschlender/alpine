ARG ALPINE_VERSION=3.22

FROM "alpine:${ALPINE_VERSION}"

ARG GROUP=user
ARG GROUP_ID=1000
ARG TIMEZONE=Europe/Berlin
ARG USER=user
ARG USER_ID=1000

RUN set -e -u -x; \
    apk update; \
    apk add --no-cache bash bash-completion nano shadow tzdata

RUN set -e -u -x; \
    cp "/usr/share/zoneinfo/${TIMEZONE}" /etc/localtime; \
    addgroup --gid "${GROUP_ID}" "${GROUP}"; \
    adduser --disabled-password --ingroup "${GROUP}" --home "/home/${USER}" --shell /bin/bash --uid "${USER_ID}" "${USER}"; \
    chown --recursive "${USER}:${GROUP}" "/home/${USER}"; \
    chmod -R 0750 "/home/${USER}"

COPY docker/.bashrc /root/
COPY --chown="${USER}:${GROUP}" docker/.bashrc "/home/${USER}/"
COPY docker/entrypoint.sh /usr/local/bin/

ENTRYPOINT ["entrypoint.sh"]
