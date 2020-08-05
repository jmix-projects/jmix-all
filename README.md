# Jmix-all Project

A project that aggregates all Jmix modules. It is designed to provide transparent navigation and refactoring in an IDE.  

After cloning the project, run `./clone-subprojects` to checkout Jmix modules and Gradle plugins. 

Gradle plugins are included as separate builds. When you import the project and build modules, snapshots published on `https://nexus.jmix.io` are used. If you change the plugins and want to test them on the modules, publish plugins to `.m2`:

```
./gradlew -b jmix-build/build.gradle publishToMavenLocal
./gradlew -b jmix-gradle-plugin/build.gradle publishToMavenLocal
```