## Gradle is code !

Java

```java
import java.io.File;

class MyClass {
    String parentDir = new File("test.txt").getAbsoluteFile().getParentPath();
}
```

Kotlin

```kotlin
val parentDir = File("test.txt").absoluteFile.parent
```

Gradle

```kotlin
val parentDir = file("test.txt").absoluteFile.parent       
```
