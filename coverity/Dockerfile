FROM ubuntu:22.04

RUN apt-get update && apt-get install -y \
    build-essential \
    wget \
    curl \
    unzip \
    openjdk-17-jdk \
    python3 \
    git

# Add your Coverity analysis CLI archive to this folder before building
COPY cov-analysis-linux64-2023.12.tar.gz /opt/
WORKDIR /opt

RUN tar -xzf cov-analysis-linux64-2023.12.tar.gz && \
    rm cov-analysis-linux64-2023.12.tar.gz

ENV PATH="/opt/cov-analysis-linux64-2023.12/bin:$PATH"

ENTRYPOINT ["cov-build"]
