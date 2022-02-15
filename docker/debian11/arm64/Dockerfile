FROM	debian:bullseye-20210902

COPY	scripts/install-deps.sh        /tmp
COPY    apt-sources.list        /etc/apt/sources.list

RUN     apt-get update -y \
        && apt-get install -y \
        --no-install-recommends 

RUN 	/tmp/install-deps.sh -a --install-packages --install-do-deps-distro debian11

VOLUME /code
WORKDIR /code
