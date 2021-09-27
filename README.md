# Which Version of JDK Should I Use?

There are plenty of Java™ Development Kits (JDK) distributions available.  
Pretty much all of them build on the source code of the [OpenJDK](https://openjdk.java.net), which is the open source reference implementation of the Java SE Platform Specification.  
The distributions differ in licences, commercial support, supported platforms, and update frequency.

## TL;DR

Use [Adoptium Eclipse Temurin OpenJDK 17](https://adoptium.net/releases.html?variant=openjdk17&jvmVariant=hotspot) and make sure your local version matches the CI and production version. 

## Decision Tree

Use the same JDK for development, CI, and production. 

So, how do you run your services in production?

* I don`t know -> Adoptium 11 
* Kubernetes or Docker -> Adoptium 11 
* Directly on cloud compute instances -> Your cloud vendor`s OpenJDK build
* Lambda/Serverless -> Oracle GraalVM 


## Releases

Under the current [JDK release model](https://openjdk.java.net/projects/jdk/), a new feature release with a new major version number is planned every six months, in March and September. Each feature release will get two updates before the next feature release.

Every three years, the September release will be a Long term release (LTS), which gets updates for at least three years (and possibly longer).

JDK Version	| Type | Release Date |	Description
--- | --- | --- | ---
*8   | LTS     | 03/2014 | Last LTS version under previous release model. No more free update by Oracle. AdoptOpenJDK [plans updates](https://adoptopenjdk.net/support.html) until 05/2026. Anyway, upgrate to a new release is strongly recommended!*
9   | Feature | 09/2017	| New release model was introduced.
10  | Feature | 03/2018	| 
11  | LTS     | 09/2018	| Widely used LTS version. Plan upgrade to version 17 within the next months is recommended.
12  | Feature | 03/2019	| 
13  | Feature | 09/2019	| 
14  | Feature | 03/2020	| 
15  | Feature | 09/2020	| 
16  | Feature | 03/2021	| 
17  | LTS     | 09/2021	| Current LTS version.


## Distributions

### openjdk.java.net

The OpenJDK project is mangaged using http://openjdk.java.net/, where you can find specifications, source code, and mailing lists.
But there are no builds that you can download.

### OpenJDK builds by Oracle (jdk.java.net)

Oracle provides OpenJDK builds for Linux, macOS and windows in a compressed archive format.

These builds will only be updated for a 6 month period. Updates and security patches will not be available after this short period.
E.g. the latest OpenJDK 11 build was [11.0.2+9](https://jdk.java.net/archive/) while the current OpenJDK version is [11.0.12+7](https://wiki.openjdk.java.net/display/JDKUpdates/JDK11u).

👎 Do not use _OpenJDK builds by Oracle_.


### Oracle Java SE Development Kit (JDK)

Oracle also has a commercial version of the OpenJDK, which are based on the exactly same sources of the OpenJDK: The Oracle Java SE Development Kit (JDK).
Oracle provides updates regular updates and security patches for these builds, especially 

The main issue with these builds is Oracle's licensing policy.

Until version 10 builds where published under the [Oracle Binary Code License Agreement](https://www.oracle.com/de/downloads/licenses/binary-code-license.html), which effectivly allowed the builds to be use for commercial projects.

With version 11 to version 16 builds were published under the [Oracle Technology Network License Agreement for Oracle Java SE](https://www.oracle.com/downloads/licenses/javase-license1.html), which required a fee-based license for usage in production.
This is why many new distributions of the OpenJDK have emerged.

Version 17 is published under the [Oracle No-Fee Terms and Conditions (NFTC)](https://www.oracle.com/downloads/licenses/no-fee-license.html), which allows the usage of the builds for running _internal business operations_. Unfortunally, it is not defined, what this means. Is a public website running _internal business operations_?
 
Also, based on this volatile licensing history, it is not predictable, how future version will be licensed.

👎 Do not use _Oracle Java SE Development Kit (JDK)_, unless you know, what you are doing.


### Adoptium Adoptium Eclipse Temurin 
TBD

### AdoptOpenJDK
TBD

### Azul Zulu
TBD

### BellSoft Liberica JDK
TBD


### Cloud Vendor Builds

Since Oracle changed the support and license policy for its OpenJDK builds, major cloud providers (which run many, many Java applications) decided to establish their own managed OpenJDK builds and providing long-term updates. Apparantly, this is to avoid risks, especially lawsuits against Oracle.

#### Amazon Corretto

https://aws.amazon.com/de/corretto/
Official Docker Images: https://hub.docker.com/_/amazoncorretto


#### Alibaba
#### Microsoft Build of OpenJDK
#### SapMachine
#### Red Hat OpenJDK




## Docker Images
TBD


## FAQs

### What is the best way to install a JDK for local development?

### What is the difference between JDK and JRE?

### What should I install for a Java desktop application?



## Contributions

Java and OpenJDK are trademarks or registered trademarks of Oracle and/or its affiliates.
