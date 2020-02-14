## Dependencies

* Dependencies are downloaded and put in your local cache.
* Gradle is compatible with Maven repositories.

```kotlin
repositories {
    mavenCentral()
}
dependencies {
    implementation("org.apache.commons", "commons-lang3", "3.0")
    testImplementation("junit:junit:4.+")
    testRuntimeOnly("com.h2database:h2")
}
```

You can also define *runtime* or *testRuntime* dependencies.
