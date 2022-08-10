# docker_android_app_builder

Dockerfiles that provide Android app building environments. <br/>
Without pre-installed Gradle, SDK platforms, and SDK build-tools, makes the image size smaller. 
 - [latest](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?page=1&ordering=last_updated&name=latest)
   - latest is currently the same as temurin11-2022.
 - [temurin11-2022](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?page=1&ordering=last_updated&name=temurin11-2022)  
 - [temurin8-2022](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?page=1&ordering=last_updated&name=temurin8-2022)  
 - [openjdk11-2022](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?page=1&ordering=last_updated&name=openjdk11-2022)  
 - [openjdk8-2022](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?page=1&ordering=last_updated&name=openjdk8-2022)  
 - [debian-2022](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?page=1&ordering=last_updated&name=debian-2022)

## temurin11-2022 Info

- [Dockerfile](/jdk11-2022/eclipse-temurin/Dockerfile)
- [Dockerhub](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?name=temurin11-2022&page=1&ordering=last_updated)
- Size: Compressed:797.12MB, downloded: 1.55GB
- OS: Ubuntu 22.04.1 LTS (jammy)
- JDK: openjdk version "11.0.16" 2022-07-19
- git: git version 2.34.1
- cmdline-tools 7.0
- other tools: wget, unzip
- JAVA_HOME = /opt/java/openjdk
- ANDROID_SDK_ROOT = /opt/android-sdk
- pwd = /home/android_proj

## temurin8-2022 Info

- [Dockerfile](/jdk8-2022/eclipse-temurin/Dockerfile)
- [Dockerhub](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?name=temurin8-2022&page=1&ordering=last_updated)
- Size: Compressed:710.19MB, downloded: 1.43GB
- OS: Ubuntu 22.04.1 LTS (jammy)
- JDK: openjdk version "1.8.0_342"
- git: git version 2.34.1
- cmdline-tools 7.0
- other tools: wget, unzip
- JAVA_HOME = /opt/java/openjdk
- ANDROID_SDK_ROOT = /opt/android-sdk
- pwd = /home/android_proj

## jdk11-2022 Info

- [Dockerfile](/jdk11-2022/openjdk/Dockerfile)
- [Dockerhub](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?name=jdk11-2022&page=1&ordering=last_updated)
- Size: Compressed:698.76MB, downloded: 1.41GB
- OS: Debian GNU/Linux 11 (bullseye)
- JDK: openjdk version "11.0.16" 2022-07-19
- git: git version 2.30.2
- cmdline-tools 7.0
- other tools: wget, unzip
- JAVA_HOME = /usr/local/openjdk-11
- ANDROID_SDK_ROOT = /opt/android-sdk
- pwd = /home/android_proj

## jdk8-2022 Info

- [Dockerfile](/jdk8-2022/openjdk/Dockerfile)
- [Dockerhub](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?name=jdk8-2022&page=1&ordering=last_updated)
- Size: Compressed:790.47MB, downloded: 1.54GB
- OS: Debian GNU/Linux 11 (bullseye)
- JDK: openjdk version "1.8.0_342"
- git: git version 2.30.2
- cmdline-tools 7.0
- other tools: wget, unzip
- JAVA_HOME = /usr/local/openjdk-8
- ANDROID_SDK_ROOT = /opt/android-sdk
- pwd = /home/android_proj

## debian-2022 Info

- [Dockerfile](/debian-2022/Dockerfile)
- [Dockerhub](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?name=debian-2022&page=1&ordering=last_updated)
- Size: Compressed:796.04MB, downloded: 1.55GB
- OS: Debian GNU/Linux 11 (bullseye)
- JDK: openjdk version "11.0.14.1" 2022-02-08
- git: git version 2.30.2
- cmdline-tools 
- other tools: wget, unzip
- JAVA_HOME = /usr/local/openjdk-11
- ANDROID_SDK_ROOT = /opt/android-sdk
- pwd = /home/android_proj

## Test this Docker image locally.

 - install [Docker](https://www.docker.com/)
 - Pull the image and run a container. And exec sh in the container: 
   ```
   docker run --rm -it snoykuo/android-app-builder /bin/sh
   ```
 - Clone a native Android project and cd into the project dir: 
   ```
   git clone https://github.com/Snoy-Kuo/hello_compose.git && cd "$(basename "$_" .git)"
   ```
 - Build release version APK: 
   ```
   ./gradlew assembleRelease
   ```
   - This will download Gradle, SDK Build-Tools, SDK Platform for the first time.

## Build env

 - macOS 12.4 (Monterey) x64
 - Docker version 20.10.17, build 100c701
 - Docker Desktop 4.10.1 (82475)

 ## References

 - [在docker搭建android編譯打包環境實踐](https://www.itread01.com/hkcfhkxi.html)
 - [Docker images for Android development](https://github.com/mreichelt/docker-android)
 - [把 Docker Image Push 到 Docker Hub](https://ithelp.ithome.com.tw/articles/10191139)

 ## Todos

 - add Apline version.
