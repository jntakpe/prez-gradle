## Phases

```groovy
task("hello") {
    doFirst {
        println("This is executed first during the execution phase.")
    }
    doLast {
        println("This is executed last during the execution phase.")
    }
    println("This is executed during the configuration phase.")
}
```

<img src="lib/images/phases.png" alt="Phases" style="height: 20vh" />
