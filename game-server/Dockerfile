ARG JAVA_VERSION

FROM busybox as downloader

WORKDIR /dl

ARG SERVER_DOWNLOAD_URL
ADD $SERVER_DOWNLOAD_URL /dl

RUN unzip *.zip \
    && rm *.zip \
    && dir=$(find . -mindepth 1 -maxdepth 1 -type d) \
    && mv "${dir}" ./server \
    && rm -rf ./server/jre

FROM $JAVA_VERSION

COPY --from=downloader /dl/server /necesse-server

WORKDIR /necesse-server

ENTRYPOINT [ "java", "-jar", "Server.jar", "-nogui" ]
