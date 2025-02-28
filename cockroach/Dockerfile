FROM debian:bookworm

RUN apt-get update && \
    apt-get install -y curl && \
    curl https://binaries.cockroachdb.com/cockroach-latest.linux-amd64.tgz | tar -xz && \
    cp -i cockroach-*/cockroach /usr/local/bin/ && \
    rm -rf cockroach-* && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*
