FROM alpine:3.11

ARG GOLLUM_USER_ID=1000
ARG GOLLUM_GROUP_ID=1000
ARG GOLLUM_VERSION=5.0.1

RUN apk update && \
    apk upgrade && \
    apk add --update --no-cache ruby git ruby-rake && \
    apk add --update --no-cache --virtual .build-deps cmake ruby-dev ruby-rdoc \
        libffi-dev build-base git zlib-dev icu-dev openssl-dev && \
    gem install --no-document --version ${GOLLUM_VERSION} gollum && \
    apk del .build-deps && \
    rm -rf /root/src /tmp/* /usr/share/man /var/cache/apk/* && \
    addgroup -g ${GOLLUM_GROUP_ID} -S gollum && \
    adduser -u ${GOLLUM_USER_ID} -S gollum -G gollum

USER gollum

WORKDIR /repo
VOLUME /repo
EXPOSE 4567
CMD ["/usr/bin/gollum"]
