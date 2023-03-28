FROM ubuntu:20.04

# Set TimeZone
ENV TZ=Asia/Tokyo
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezon

# Install packages
RUN apt-get update \
  && apt-get install -y git unzip clang pkg-config libgtk-3-dev curl cmake ninja-build

# Create user
RUN adduser app --disabled-password --gecos "" \
  && usermod -aG root app
USER app
WORKDIR /home/app

# Install flutter
RUN git clone https://github.com/flutter/flutter.git /home/app/opt/flutter
ENV PATH=$PATH:/home/app/opt/flutter/bin

