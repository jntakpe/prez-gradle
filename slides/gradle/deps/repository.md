## Repositories

```kotlin
repositories {
    mavenLocal()
    mavenCentral()
    maven {
        url = uri("https://my.nexus.registry/gradle-repo")
        authentication { create<BasicAuthentication>("basic") }
        credentials { 
            username = "jdoe"
            password = "changeme"
         }
    }
}


```
