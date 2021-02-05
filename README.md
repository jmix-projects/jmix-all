# Jmix-all Project

A project that aggregates all Jmix modules. It is designed to provide transparent navigation and refactoring in an IDE.  

1. If you have access to Jmix private repositories on GitHub, set `JMIX_USE_PRIVATE_REPOSITORIES` environment variable to any non-empty value. Restart OS to make sure it works.

    If you don't have access to the private repositories, the project will work with the public ones only. 

2. After cloning the project, run `./clone-subprojects` to checkout Jmix modules and Gradle plugins.

3. Open `jmix-all` in IntelliJ IDEA and import Gradle project. 

Gradle plugins are included as separate builds. When you import the project and build modules, snapshots published on `https://nexus.jmix.io` are used. If you change the plugins and want to test them on the modules, publish plugins to `.m2`:

```
./gradlew -b jmix-build/build.gradle publishToMavenLocal
./gradlew -b jmix-gradle-plugin/build.gradle publishToMavenLocal
```