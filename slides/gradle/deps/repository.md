## Repositories

```kotlin
repositories {
    mavenCentral()
    jcenter()
    maven {
        url = uri("$repositoryUrl/gradle-repo")
        authentication { create<BasicAuthentication>("basic") }
        credentials { 
            username = repositoryUser
            password = repositoryPassword
         }
    }
}


```
