ARG     BASE_IMAGE_VERSION=bullseye-20210902-slim

FROM    debian:${BASE_IMAGE_VERSION}

COPY    scripts/install-deps.sh /tmp
COPY    apt-sources.list        /etc/apt/sources.list

RUN     apt-get update -y \
        && apt-get install -y \
        --no-install-recommends

RUN     /tmp/install-deps.sh -a --install-packages --install-do-deps-distro debian11

VOLUME  /code

WORKDIR /code
