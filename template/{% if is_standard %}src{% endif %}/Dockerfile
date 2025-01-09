FROM ubuntu:24.04@sha256:80dd3c3b9c6cecb9f1667e9290b3bc61b78c2678c02cbdae5f0fea92cc6734ab

# renovate: datasource=repology depName=ubuntu_24_04/nano versioning=loose
ENV NANO_VERSION=7.2-2ubuntu0.1

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update \
    && apt-get install --no-install-recommends -y \
    nano="${NANO_VERSION}" \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

CMD ["nano", "--version"]