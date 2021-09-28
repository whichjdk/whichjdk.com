# Which Version of JDK Should I Use?

There are plenty of Java™ Development Kits (JDK) distributions available.  
Pretty much all of them build on the source code of the [OpenJDK](https://openjdk.java.net), which is the open source reference implementation of the Java SE Platform Specification.  
The distributions differ in licenses, commercial support, supported platforms, and update frequency.

## TL;DR

Use [Adoptium Eclipse Temurin OpenJDK 17](https://adoptium.net/releases.html?variant=openjdk17&jvmVariant=hotspot) and make sure your local version matches the CI and production version. 

## Releases

Under the current [JDK release model](https://openjdk.java.net/projects/jdk/), a new feature release with a new major version number is planned every six months, in March and September. Additionally, there are quarterly bug fix updates.

Every three years, the September release will be a Long term release (LTS), which gets updates for at least three years (and possibly longer).

JDK Version	| Type    | Release Date | New	Features         | Description
----------- | ------- | ------------ | ---------------------| ---
**8**       | **LTS** | **03/2014**  | Lambdas              |  Last LTS version under previous release model. Free updates by Oracle ended. AdoptOpenJDK [plans updates](https://adoptopenjdk.net/support.html) until 05/2026. Anyway, upgrade to a 11 or 17 is strongly recommended!
9           | Feature | 09/2017	     | Modules              | New release model was introduced. EOL. Upgrade to 11 or 17 now!
10          | Feature | 03/2018	     | var                  | EOL. Upgrade to 11 or 17 now!
**11**      | **LTS** | **09/2018**	 | New HTTP Client      | Widely used LTS version. Plan upgrade to version 17 within the next months is recommended.
12          | Feature | 03/2019	     |                      | EOL. Upgrade to 17 now!
13          | Feature | 09/2019	     |                      | EOL. Upgrade to 17 now!
14          | Feature | 03/2020	     | Switch expressions   | EOL. Upgrade to 17 now!
15          | Feature | 09/2020	     | Text blocks          | EOL. Upgrade to 17 now!
16          | Feature | 03/2021	     | Records              | EOL. Upgrade to 17 now!
**17**      | **LTS** | **09/2021**	 | Sealed Classes       | Current LTS version.

Users are adviced to decide, if they stick with the latest LTS version, or if they go with the latest feature release and upgrade to the new feature release every six months. If uncertain, it is a good advice to stick with the LTS version, as Java is quite a stable programming language.

The OpenJDK project is mangaged using [openjdk.java.net](https://openjdk.java.net), where you can find specifications, source code, and mailing lists.
But there are no builds that you can download.

## Distributions

### OpenJDK builds by Oracle (jdk.java.net)

Oracle provides OpenJDK builds for Linux, macOS and windows in a compressed archive format.

These builds will only be updated for a 6 month period. Updates and security patches will not be available after this short period. This also applies for LTS versions! E.g. the latest OpenJDK 11 build was [11.0.2+9](https://jdk.java.net/archive/) while the current OpenJDK version is [11.0.12+7](https://wiki.openjdk.java.net/display/JDKUpdates/JDK11u).

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


### Adoptium Eclipse Temurin 

[Website](https://adoptium.net)
[Releases](https://adoptium.net/archive.html)
[Source](https://github.com/adoptium/temurin-build)
[Docker Images](https://hub.docker.com/_/eclipse-temurin/)

Eclipse Adoptium is a top-level project under the Eclipse Foundation, which provides resources and a professional governance model for open source software.
The Adoptium Working Group consists of major companies and organizations that have a strategic interest in the Java technology, including Red Hat, IBM, Microsoft, Azul, and the iJUG. The former AdoptOpenJDK project has moved to Eclipse Adoptium.

The Adoptium OpenJDK builds are called _Eclipse Temurin_ to distinguish to project and the builds.
In contrast to AdoptOpenJDK, Adoptium will not provide builds with the OpenJ9 virtual machine.

The Eclipse Temurin buids are high-quality, vendor-neutral, and TCK-tested under a permissive license.
Adoptium ensures, it will continue to build binaries for LTS releases as long as the corresponding upstream source is actively maintained.

👍 Adoptium Eclipse Temurin OpenJDK builds are highly recommended.

### AdoptOpenJDK
TBD

### Azul Zulu
TBD

### BellSoft Liberica JDK
TBD

### IBM Semeru
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
