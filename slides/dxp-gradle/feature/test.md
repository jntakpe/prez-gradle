## Testing automation

* [Configures]((https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/tree/master/src/main/kotlin/com/soprabanking/dxp/project)) API contracts including :
    * Producer side contract based tests
    * Contract remote publication and retrieval
* [Configures](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/DxpGradle.kt#L46)
 third party system mocking strategy
    * Downloads and startup an embedded MongoDB, Redis or H2 depending on dependencies
* [Configures](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/Test.kt#L13)
 unit tests
    * Configures JUnit platform
    * Configures failing modes (fail-fast), logging levels, exceptions, ...
