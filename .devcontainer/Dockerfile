# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.238.0/containers/debian/.devcontainer/base.Dockerfile

# [Choice] Debian version (use bullseye on local arm64/Apple Silicon): bullseye, buster
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

COPY ./wkhtmltox_0.12.6.1-2.bullseye_*.deb /tmp

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
      fontconfig \
      libfreetype6 \
      libjpeg62-turbo \
      libpng16-16 \
      libx11-6 \
      libxcb1 \
      libxext6 \
      libxrender1 \
      xfonts-75dpi \
      xfonts-base \
    && dpkg -i /tmp/wkhtmltox_0.12.6.1-2.bullseye_amd64.deb /tmp/wkhtmltox_0.12.6.1-2.bullseye_arm64.deb \
    ; apt-get clean \
    && rm -rf /var/cache/apt/archives/* \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* \
    && truncate -s 0 /var/log/*log