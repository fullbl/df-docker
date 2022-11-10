FROM debian:11.5-slim

RUN apt-get update \
 && DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    bzip2 \
    ca-certificates \
    curl \
    libglu1-mesa \
    libgtk2.0-0 \
    libncursesw5 \
    libopenal1 \
    libsdl-image1.2 \
    libsdl-ttf2.0-0 \
    locales \
    unzip \
 && apt-get clean \
 && rm -rf /var/lib/apt/lists/*

ENV LANG=en_US.UTF-8 LANGUAGE=en_US:en LC_ALL=en_US.UTF-8 \
    DF_VERSION=47_04 \
    DF_ARCHIVE_SHA256=1de5872bf3ac32906a0082129ec88d6879b6ac7059a3513607d628090b1328e6

RUN LC_ALL=C locale-gen en_US.UTF-8 \
 && mkdir -p /df_linux \
 && cd / \
 && curl -LSo /df_linux.tar.bz2 https://fullbl.it/df_${DF_VERSION}_linux.tar.bz2 \
 && echo "${DF_ARCHIVE_SHA256} *df_linux.tar.bz2" | sha256sum -c \
 && tar -xjf /df_linux.tar.bz2 df_linux \
 && rm df_linux.tar.bz2 \
 && chmod -x+X -R /df_linux \
 && rm /df_linux/libs/libgcc_s.so.1 /df_linux/libs/libstdc++.so.6 \
 && mkdir -p /df_linux/data/save /df_linux/data/movies \

WORKDIR /df_linux
VOLUME /df_linux/data/save
VOLUME /df_linux/data/movies

CMD ["./df"]


