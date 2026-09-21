FROM swift:6.3-noble

RUN export DEBIAN_FRONTEND=noninteractive DEBCONF_NONINTERACTIVE_SEEN=true \
    && apt-get -q update \
    && apt-get -q install -y --no-install-recommends \
      ca-certificates \
      curl \
      gnupg \
      libjemalloc-dev \
      zstd \
      tzdata \
      libcurl4 \
    && install -m 0755 -d /etc/apt/keyrings \
    && curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /tmp/docker.asc \
    && gpg --dearmor -o /etc/apt/keyrings/docker.gpg /tmp/docker.asc \
    && rm -f /tmp/docker.asc \
    && chmod a+r /etc/apt/keyrings/docker.gpg \
    && . /etc/os-release \
    && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu ${VERSION_CODENAME} stable" > /etc/apt/sources.list.d/docker.list \
    && apt-get -q update \
    && apt-get -q install -y --no-install-recommends \
      docker-ce-cli \
      docker-buildx-plugin \
    && rm -rf /var/lib/apt/lists/*
