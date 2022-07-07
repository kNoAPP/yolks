FROM        --platform=$TARGETOS/$TARGETARCH dart:2.17

LABEL       author="Alden Bansemer" maintainer="alden@knoban.com"

RUN         apt update \
            && apt -y install ffmpeg iproute2 git sqlite ca-certificates openssl dnsutils zip tar curl \
            && useradd -m -d /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]