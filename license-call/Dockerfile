FROM alpine:latest

RUN apk add --update \
    curl \
    && rm -rf /var/cache/apk/*

COPY license.json /

ENTRYPOINT ["curl", "-XPUT", "-d", "@license.json"]
