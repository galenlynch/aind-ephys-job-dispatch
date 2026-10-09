# hash:sha256:0fca3f034e573b9621dca52296cc5ee29a686e8a10df89f2133f98e7157e408b
ARG REGISTRY_HOST
FROM $REGISTRY_HOST/codeocean/python-slim-uv:main-5692e50

ARG DEBIAN_FRONTEND=noninteractive
ARG GIT_ASKPASS
COPY git-ask-pass /

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        procps=2:4.0.4-9 \
    && rm -rf /var/lib/apt/lists/*

COPY postInstall /
RUN --mount=type=secret,id=secrets . /run/secrets/secrets \
    && /postInstall
