FROM alpine:3.17.0

RUN set -ex; \
    \
    apk add --update --no-cache \
        bash \
        borgbackup \
        rsync \
        fuse \
        py3-llfuse \
        jq \
    ; \
    rm -rf /var/lib/apt/lists/*

VOLUME /root

COPY start.sh /usr/bin/
COPY backupscript.sh /
RUN chmod +x /usr/bin/start.sh; \
    chmod +x /backupscript.sh

USER root
ENTRYPOINT ["start.sh"]