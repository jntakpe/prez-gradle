## Depends on

```kotlin
val hello by tasks.registering {
    doLast {
        print("Hello, ")
    }
}

task("world") {
    dependsOn(hello)
    doLast {
        print("World!")
    }
}
```

<img src="lib/images/hello-world-task.png" alt="Hello" style="height: 10vh" />
