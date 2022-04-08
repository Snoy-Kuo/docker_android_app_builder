# docker_android_app_builder

Dockerfiles that provide Android app building environments. <br/>
Without pre-installed Gradle, SDK platforms, and SDK build-tools, makes the image size smaller. 
 - [snoykuo/android-app-builder:debian-2022](https://hub.docker.com/repository/docker/snoykuo/android-app-builder/tags?page=1&ordering=last_updated&name=debian-2022)

## debian-2022 Info

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
 - Pull the image and run a container: `docker run --name container1 snoykuo/android-app-builder:debian-2022`
 - Exec sh in the container: `docker exec -it container1 /bin/sh`
 - Clone a native Android project and cd into the project dir: `git clone https://github.com/Snoy-Kuo/hello_compose.git && cd "$(basename "$_" .git)"`
 - Build release version APK: `./gradlew assembleRelease`
   - This will download Gradle, SDK Build-Tools, SDK Platform for the first time.

## Build env

 - macOS 12.2.1 (Monterey) x64
 - Docker version 20.10.13, build a224086
 - Docker Desktop 4.6.1 (76265)

 ## References

 - [在docker搭建android編譯打包環境實踐](https://www.itread01.com/hkcfhkxi.html)
 - [Docker images for Android development](https://github.com/mreichelt/docker-android)
 - [把 Docker Image Push 到 Docker Hub](https://ithelp.ithome.com.tw/articles/10191139)

 ## Todos

 - add Apline version.
 - add Ubuntu version.
