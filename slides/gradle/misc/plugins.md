## Plugins

Any Gradle script can be a plug-in :

```kotlin
//Binary plugins
plugins {
    java
    `maven-publish`
    id("org.sonarqube") version "2.8"
}
// Script plugins
apply(from = "my-gradle-script.gradle")
apply(from = "http://www.some-site.com/other-script.gradle")

```

You can find the full list of standards plugins : [https://docs.gradle.org/current/userguide/standard_plugins.html](https://docs.gradle.org/current/userguide/standard_plugins.html)
