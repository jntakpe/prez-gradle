## With DxP Gradle

```kotlin
import com.soprabanking.dxp.dxp
import com.soprabanking.dxp.schemas

dxpJavaApplication()

dependencies {
    implementation(dxp("api"))
    implementation(dxp("cache"))
    implementation(dxp("mongodb"))
    implementation(dxp("security"))
    implementation(dxp("kafka"))
    compileOnly(schemas(dxp("kafka")))
    runtimeOnly(dxp("monitor"))
    testImplementation(dxp("test"))
}
```
