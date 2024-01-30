ARG ALPINE_VERSION=3.19

FROM alpine:${ALPINE_VERSION}

ARG GROUP=user
ARG GROUP_ID=1000
ARG TIMEZONE=Europe/Berlin
ARG USER=user
ARG USER_ID=1000

RUN apk update; \
    apk add --no-cache bash bash-completion nano shadow tzdata

RUN set -e -u; \
    cp /usr/share/zoneinfo/${TIMEZONE} /etc/localtime; \
    addgroup --gid ${GROUP_ID} --system ${GROUP}; \
    adduser --ingroup ${GROUP} --home /${USER} --shell /bin/bash --system --uid ${USER_ID} ${USER}

RUN set -e -u; \
    chown --recursive ${USER}:${USER} /${USER}

COPY docker/.bashrc /root
COPY --chown=${USER}:${USER} docker/.bashrc /${USER}
COPY docker/entrypoint.sh /usr/local/bin

ENTRYPOINT ["entrypoint.sh"]
