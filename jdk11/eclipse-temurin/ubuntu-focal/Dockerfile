# base on 'eclipse-temurin:11-jdk-focal' image
FROM eclipse-temurin:11-jdk-focal

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
#9645777 10.0 ->jdk11
#10406996 11.0 -> jdk17
ARG cmdToolUrl="https://dl.google.com/android/repository/commandlinetools-linux-9645777_latest.zip"
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

#docker build -t snoykuo/android-app-builder:temurin11-focal . --no-cache