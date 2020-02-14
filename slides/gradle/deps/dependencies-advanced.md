## Advanced dependencies

```kotlin
val spring = listOf(
    "org.springframework.spring-security:5.0.0.RELEASE",
    "org.springframework.spring-web:5.0.0.RELEASE"
)
dependencies {
    implementation(files("lib/a.jar", "lib/b.jar"))
    implementation(spring)
    runtimeOnly(fileTree("libs") { includes += "*.jar"})
}
```
