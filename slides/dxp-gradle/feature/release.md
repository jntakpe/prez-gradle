## Release management

* [Automatically](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/project/DxpProject.kt#L98)
 set project version based on Git's tag or branch
* [Automatically](https://innersource.soprasteria.com/dxp/dxp-core/common-librairies/dxp-gradle/blob/master/src/main/kotlin/com/soprabanking/dxp/Changelog.kt)
 create changelog based on project commit's
    * build: Changes that affect the build system or external dependencies
    * docs: Documentation only changes
    * feat: A new feature
    * fix: A bug fix
    * perf: A code change that improves performance
    * refactor: A code change that neither fixes a bug nor adds a feature
    * style: Changes that do not affect the meaning of the code
    * test: Adding missing tests or correcting existing tests
    * chore: Other changes that don't modify src or test files
