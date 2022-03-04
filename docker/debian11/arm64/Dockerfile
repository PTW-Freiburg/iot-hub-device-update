ARG     BASE_IMAGE_VERSION=bullseye-20210902-slim

FROM    debian:${BASE_IMAGE_VERSION}

COPY    scripts/install-deps.sh /tmp
COPY    apt-sources.list        /etc/apt/sources.list

RUN     apt-get update -y \
        && apt-get install -y \
        --no-install-recommends

ARG     DO_CLIENT_SOURCE_BRANCH=feature/debian11-arm64-build
ARG     AZURE_IOT_SDK_SOURCE_BRANCH=LTS_01_2022_Ref01
ARG     AZURE_BLOB_STORAGE_FILE_UPLOAD_UILITY_SOURCE_BRANCH=main
ARG     CATCH2_SOURCE_BRANCH=v2.13.8

RUN     /tmp/install-deps.sh -a --install-packages --install-do-deps-distro debian11 --do-ref ${DO_CLIENT_SOURCE_BRANCH} --azure-iot-sdk-ref ${AZURE_IOT_SDK_SOURCE_BRANCH} --abs-file-upload-utility-ref ${AZURE_BLOB_STORAGE_FILE_UPLOAD_UILITY_SOURCE_BRANCH} --catch2-ref

VOLUME  /code

WORKDIR /code
