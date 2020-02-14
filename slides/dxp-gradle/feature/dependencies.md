## Dependencies management

* [Provides](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/Dependencies.kt)
 helpers to import commons libraries, other libraries, stubs and schemas
* [Prevents](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/Dependencies.kt#L81)
 snapshot usage in releases
* [Configures](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/Owasp.kt)
 Owasp to check dependencies and update a CVS registry
* [Configures](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/Dxp.kt#L24)
 dependency strategies and excludes unwanted modules
* [Configures](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/Versions.kt)
 default dependencies versions
* [Configures](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/DependencyUpdates.kt)
  automatic dependency updates plugin
