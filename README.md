# Jmix-all Project

A project that aggregates all Jmix modules. It is designed to provide transparent navigation and refactoring in an IDE.  

1. If you have access to Jmix private repositories on GitHub, set `JMIX_USE_PRIVATE_REPOSITORIES` environment variable to any non-empty value. Restart OS to make sure it works.

    If you don't have access to the private repositories, the project will work with the public ones only. 

2. After cloning the project, run `./clone-subprojects` to checkout Jmix modules and Gradle plugins.

3. Open `jmix-all` in IntelliJ IDEA and import Gradle project. 

Make sure you have increased heap size for Gradle using the [org.gradle.jvmargs](https://docs.gradle.org/current/userguide/build_environment.html) property. In order to do that edit the `~/.gradle/gradle.properties` file and set the `-Xmx` parameter in the `org.gradle.jvmargs property`. The recommended value is 2048m or more, for example:

```
org.gradle.jvmargs=-Xmx2048m
```

Gradle plugins are included as separate builds. When you import the project and build modules, snapshots published on `https://nexus.jmix.io` are used. If you change the plugins and want to test them on the modules, publish plugins to `.m2`:

```
./gradlew -b jmix-build/build.gradle publishToMavenLocal
./gradlew -b jmix-gradle-plugin/build.gradle publishToMavenLocal
```