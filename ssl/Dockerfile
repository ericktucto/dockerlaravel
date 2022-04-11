FROM alpine:3.15
LABEL "Author: Erick Tucto"
LABEL "Email: erick.tucto@outlook.com"
LABEL "Github: https://github.com/ErickTucto"
LABEL "Website: https://ericktucto.com"

RUN apk upgrade --update-cache --available && \
    apk add --no-cache openssl && \
    mkdir -p /var/ssl/keys && \
    rm -rf /var/cache/apk/*

COPY init-ssl new-ssl /usr/bin/
VOLUME /var/ssl/keys
WORKDIR /root
CMD ["init-ssl"]
