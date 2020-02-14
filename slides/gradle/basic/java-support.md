## Java support

```kotlin
plugins {
    java
}
```

By convention gradle assumes the following directory structure :

* *src/main/java* for production source code
* *src/test/java* for production source code
* *src/main/resources* will be included in the JAR file as resources
* *src/test/resources* will be included in the classpath used to run the tests
* *build* where Gradle outputs the build (compiled classes, jars, dependencies)
