FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

ARG QUARTO_VERSION=1.9.38

ENV DEBIAN_FRONTEND=noninteractive
ENV PATH="/opt/quarto-python/bin:${PATH}"

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        ca-certificates \
        curl \
        fontconfig \
        fonts-dejavu \
        fonts-liberation \
        fonts-noto-core \
        ghostscript \
        git \
        jq \
        make \
        python3 \
        python3-pip \
        python3-venv \
        unzip \
        wget \
        zip \
    && rm -rf /var/lib/apt/lists/*

RUN set -eux; \
    architecture="$(dpkg --print-architecture)"; \
    case "${architecture}" in \
      amd64|arm64) ;; \
      *) echo "Unsupported architecture: ${architecture}" >&2; exit 1 ;; \
    esac; \
    curl -fsSL \
      "https://github.com/quarto-dev/quarto-cli/releases/download/v${QUARTO_VERSION}/quarto-${QUARTO_VERSION}-linux-${architecture}.deb" \
      -o /tmp/quarto.deb; \
    apt-get update; \
    apt-get install -y --no-install-recommends /tmp/quarto.deb; \
    rm -f /tmp/quarto.deb; \
    rm -rf /var/lib/apt/lists/*

RUN python3 -m venv /opt/quarto-python \
    && /opt/quarto-python/bin/python -m pip install --no-cache-dir --upgrade pip \
    && /opt/quarto-python/bin/python -m pip install --no-cache-dir jupyter

USER vscode

RUN quarto install tinytex --no-prompt

RUN set -eux; \
    workdir="$(mktemp -d)"; \
    printf '%s\n' \
      '---' \
      'title: "Quarto PDF Smoke Test"' \
      'format: pdf' \
      '---' \
      '' \
      'Quarto and TinyTeX are ready.' \
      > "${workdir}/smoke.md"; \
    cd "${workdir}"; \
    quarto render smoke.md; \
    test -f smoke.pdf; \
    rm -rf "${workdir}"
