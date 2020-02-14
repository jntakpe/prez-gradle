## Without DxP Gradle

```groovy
buildscript {
    ext {
        springBootVersion = '2.0.2.RELEASE'
        springCloudContractVersion = '2.0.0.RC1'
    }
    repositories {
        mavenLocal()
        jcenter()
        maven {
            url "https://repo.spring.io/snapshot"
        }
        maven {
            url "https://repo.spring.io/milestone"
        }
    }

    dependencies {
        classpath("org.springframework.boot:spring-boot-gradle-plugin:${springBootVersion}")
        classpath("org.springframework.cloud:spring-cloud-contract-gradle-plugin:${springCloudContractVersion}")
    }
}

plugins {
    id 'org.asciidoctor.convert' version '1.5.7' apply true
    id 'com.jfrog.artifactory' version '4.6.2'
    id 'com.gradle.build-scan' version '1.13.3'
    id 'org.sonarqube' version '2.6.2' apply true
    id 'org.owasp.dependencycheck' version '3.2.0' apply true
}

apply plugin: 'java'
apply plugin: 'maven-publish'
apply plugin: 'spring-cloud-contract'
apply plugin: 'io.spring.dependency-management'

group = 'com.soprabanking.dxp'
version = '0.1.3-SNAPSHOT'
sourceCompatibility = 1.8

def appPackageName = 'tppcontrols'
def rootPackage = "${project.group}.${appPackageName}"


ext {
    snippetsDir = file("${buildDir}/generated-snippets")
}

dependencyManagement {
    imports {
        mavenBom "org.springframework.boot:spring-boot-starter-parent:${springBootVersion}"
        mavenBom "org.springframework.cloud:spring-cloud-dependencies:${springCloudVersion}"
    }
}

dependencies {
    compile("com.soprabanking.dxp:commons-api:${commonsVersion}")
    compile("com.soprabanking.dxp:commons-client:${commonsVersion}")
    compile("com.soprabanking.dxp:commons-error:${commonsVersion}")
    compile("com.soprabanking.dxp:commons-kafka:${commonsVersion}")
    compile("com.soprabanking.dxp:commons-monitor:${commonsVersion}")
    compile("com.soprabanking.dxp:commons-security:${commonsVersion}")
    compile("com.soprabanking.dxp:commons-mongodb:${commonsVersion}")
    testCompile("com.soprabanking.dxp:commons-test:${commonsVersion}")
    testCompile("com.soprabanking.dxp:service-tpp-management:${serviceTppManagementVersion}:stubs") {
        transitive = false
    }
    testRuntime("org.junit.jupiter:junit-jupiter-engine")
    testRuntime("org.junit.vintage:junit-vintage-engine")
    asciidoctor("org.springframework.restdocs:spring-restdocs-asciidoctor")
}

test {
    useJUnitPlatform()
}

asciidoctor {
    dependsOn test
    inputs.dir snippetsDir
    sources {
        include 'api-guide.adoc'
    }
}

asciidoctor.doLast {
    copy {
        from "${buildDir}/asciidoc/html5"
        into "${projectDir}/src/main/resources/static"
        include 'api-guide.html'
    }
}


artifacts {
    archives verifierStubsJar
}

artifactoryPublish {
    dependsOn build
}

publishToMavenLocal {
    dependsOn build
}

publishing {
    publications {
        mavenJava(MavenPublication) {
            from components.java
            groupId = group
        }
    }
}

repositories {
    mavenLocal()
    jcenter()
    maven {
        url "https://repo.spring.io/snapshot"
    }
    maven {
        url "https://repo.spring.io/milestone"
    }
}
artifactory {
    contextUrl = "${artifactory_contextUrl}"
    publish {
        repository {
            repoKey = 'gradle-repo-local'
            username = "${artifactory_user}"
            password = "${artifactory_password}"
            maven = true
        }
        defaults {
            publications('mavenJava', 'stubs')
        }
    }
    resolve {
        repoKey = 'jcenter'
        repository {
            repoKey = 'gradle-repo'
            username = "${artifactory_user}"
            password = "${artifactory_password}"
            maven = true
        }
    }
}
buildScan {
    setTermsOfServiceUrl("https://gradle.com/terms-of-service")
    setTermsOfServiceAgree("yes")
}
```
