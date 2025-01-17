# Use Ubuntu as the base image
FROM ubuntu:22.04

# Install dependencies
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    curl \
    wget \
    git \
    python3 \
    python3-pip \
    xz-utils && \
    apt-get clean

# Install Calibre directly from the official binary
RUN curl -L https://download.calibre-ebook.com/6.27.0/calibre-6.27.0-x86_64.txz -o /tmp/calibre.txz && \
    tar xJf /tmp/calibre.txz -C /opt && \
    ln -s /opt/calibre/calibre /usr/bin/calibre && \
    ln -s /opt/calibre/ebook-convert /usr/bin/ebook-convert && \
    # rm /tmp/calibre.txz

# Install pdftoppm for PDF to PNG conversion
RUN apt-get update && \
    apt-get install -y poppler-utils && \
    apt-get clean

# Set a default work directory
WORKDIR /workspace