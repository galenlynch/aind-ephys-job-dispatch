# hash:sha256:9ea52d8d7fcb2300ea8a13d773cafab22c128e5ed642e9662d88ff8d1c533356
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/python-slim-uv:main-5692e50

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-ask-pass /

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        procps \
    && rm -rf /var/lib/apt/lists/*

COPY postInstall /
RUN --mount=type=secret,id=secrets . /run/secrets/secrets \
    && /postInstall
