# base on 'eclipse-temurin:17-jdk-jammy' image
FROM eclipse-temurin:17-jdk-jammy

LABEL maintainer="snoykuo@gmail.com"

#Android SDK folder
ENV ANDROID_SDK_ROOT="/opt/android-sdk"

WORKDIR /tmp

# Install tools: git, wget, unzip
RUN apt-get update -qq && \ 
    apt-get install git wget unzip -qq -y > /dev/null 2>&1

# Install Android commandline tools 
#8512546 7.0 ->jdk8
#9123335 8.0 ->jdk8
#9477386 9.0
#9862592 10.0 ->jdk11
#10406996 11.0 -> jdk17
#11076708
ARG CMDLINE_VERSION_CODE="11076708"
ARG cmdToolUrl="https://dl.google.com/android/repository/commandlinetools-linux-${CMDLINE_VERSION_CODE}_latest.zip"
RUN mkdir --parents ${ANDROID_SDK_ROOT}/cmdline-tools && \
    wget --quiet --output-document=tools.zip ${cmdToolUrl} && \
    unzip -qq tools.zip  && \
    mv cmdline-tools ${ANDROID_SDK_ROOT}/cmdline-tools/tools && \
    rm -Rf /tmp/*
ENV PATH $PATH:$ANDROID_SDK_ROOT/cmdline-tools/tools/bin
RUN yes | sdkmanager 'tools' > /dev/null

# Create projects folder
RUN mkdir /home/android_proj
WORKDIR /home/android_proj

#docker build -t snoykuo/android-app-builder:temurin17-jammy . --no-cache

#for apple silicon mac: 
#docker buildx build --platform linux/amd64 -t "snoykuo/android-app-builder:temurin17-jammy" . --no-cache 