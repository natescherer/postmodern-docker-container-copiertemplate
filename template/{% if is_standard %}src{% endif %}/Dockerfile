FROM ubuntu:24.04@sha256:80dd3c3b9c6cecb9f1667e9290b3bc61b78c2678c02cbdae5f0fea92cc6734ab
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# renovate: datasource=repology depName=ubuntu_24_04/ca-certificates versioning=loose
ENV RENOVATE_CA_CERTIFICATES_VERSION=20240203

# renovate: datasource=github-releases depName=tianon/gosu
ENV RENOVATE_GOSU_VERSION=1.17

# renovate: datasource=repology depName=ubuntu_24_04/nano versioning=loose
ENV RENOVATE_NANO_VERSION=7.2-2ubuntu0.1

# renovate: datasource=repology depName=ubuntu_24_04/wget versioning=loose
ENV RENOVATE_WGET_VERSION=1.21.4-1ubuntu4.1

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
    && apt-get install --no-install-recommends -y \
    ca-certificates="${RENOVATE_CA_CERTIFICATES_VERSION}" \
    nano="${RENOVATE_NANO_VERSION}" \
    wget="${RENOVATE_WGET_VERSION}" \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN dpkgArch="$(dpkg --print-architecture | awk -F- '{ print $NF }')" \
	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$RENOVATE_GOSU_VERSION/gosu-$dpkgArch" \
	&& chmod +x /usr/local/bin/gosu \
	&& gosu --version \
	&& gosu nobody true

WORKDIR /srv/dockercontainer
COPY entrypoint.sh ./
ENTRYPOINT ["/srv/dockercontainer/entrypoint.sh"]
CMD ["nano", "--version"]