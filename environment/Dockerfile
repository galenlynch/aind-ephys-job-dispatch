# hash:sha256:b0985816fa3f40da286c65ca6edf590672272d8fbef5dc66d4295ae7a7569d87
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/mambaforge3:24.5.0-0-python3.12.4-ubuntu22.04

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-ask-pass /

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        build-essential=12.9ubuntu3 \
    && rm -rf /var/lib/apt/lists/*

RUN pip install -U --no-cache-dir \
    aind-log-utils==0.2.3 \
    hdmf-zarr==0.13.0 \
    pynwb==3.1.3 \
    s3fs==2025.5.1 \
    spikeinterface==0.104.7 \
    universal-pathlib==0.3.10 \
    wavpack-numcodecs==0.2.2
