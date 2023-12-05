FROM ubuntu:22.04

# non interactive frontend for locales
ENV DEBIAN_FRONTEND=noninteractive

# installing texlive and utils
RUN apt-get update && \
    apt-get -y install \
    texlive-latex-base \
    texlive-latex-recommended \
    texlive-latex-extra \
    texlive-full \
    libx11-dev \
    python3 \
    python3-pip \
    git \
    inkscape \
    locales && \
    rm -rf /var/lib/apt/lists/*

RUN python3 -m pip install pandas matplotlib numpy scipy

# Set Locales
RUN sed -i '/en_US.UTF-8/s/^# //g' /etc/locale.gen && locale-gen
ENV LANG en_US.UTF-8
ENV LANGUAGE en_US:en
ENV LC_ALL en_US.UTF-8
