# Which Version of JDK Should I Use?

To build and run Java applications, a Java Compiler, Java Runtime Libraries, and a Virtual Machine are required that implement the Java Platform, Standard Edition ("Java SE") specification.

The [OpenJDK](https://openjdk.java.net) is the open source reference implementation of the Java SE Specification, but it is only the source code.
Binary distributions are provided by different vendors for a number of supported platforms.
These distributions differ in licenses, commercial support, supported platforms, and update frequency.

This site gives independent, yet opinonated recommendations.


## TL;DR

✅ Recommendation: Use [Adoptium Eclipse Temurin 17](#adoptium-eclipse-temurin) and ensure that your local version matches the CI and production version.

## Releases

Under the current [JDK release model](https://openjdk.java.net/projects/jdk/), a new feature release with a new major version number is planned every six months, in March and September. Additionally, there are quarterly bug fix updates.

Every three years, the September release will be a Long-Term-Support (LTS) release, which gets updates for at least three years.

JDK Version	| Type    | Release Date | Highlights           | Recommendation
----------- | ------- | ------------ | ---------------------| ---
**8**       | **LTS** | **03/2014**  | Lambdas              |  Last LTS version under previous release model. Free updates by Oracle [ended](https://www.oracle.com/java/technologies/java-se-support-roadmap.html), but still maintained by others. Upgrade to a 11 or 17 within the next months!
9           | Feature | 09/2017	     | Modules              | New release model was introduced. EOL. Upgrade to 11 or 17 now!
10          | Feature | 03/2018	     | var                  | EOL. Upgrade to 11 or 17 now!
**11**      | **LTS** | **09/2018**	 | New HTTP Client      | Widely used LTS version. Plan upgrade to version 17 within the next months.
12          | Feature | 03/2019	     |                      | EOL. Upgrade to 17 now!
13          | Feature | 09/2019	     |                      | EOL. Upgrade to 17 now!
14          | Feature | 03/2020	     | Switch expressions   | EOL. Upgrade to 17 now!
15          | Feature | 09/2020	     | Text blocks          | EOL. Upgrade to 17 now!
16          | Feature | 03/2021	     | Records              | EOL. Upgrade to 17 now!
**17**      | **LTS** | **09/2021**	 | Sealed Classes       | Current LTS version.

You have to decide, if you want to stick with the latest LTS version, or if you go with the latest feature release and upgrade every six months.
Both ways are OK.
If uncertain, stick with the latest LTS version.

The OpenJDK project itself is mangaged on [openjdk.java.net](https://openjdk.java.net), where you can find specifications, source code, and mailing lists.
But there are no builds that you can download.
You need to choose a distribution.

## Distributions

- [OpenJDK builds by Oracle (jdk.java.net)](#openjdk-builds-by-oracle-jdkjavanet)
- [Oracle Java SE Development Kit (JDK)](#oracle-java-se-development-kit-jdk)
- [Adoptium Eclipse Temurin](#adoptium-eclipse-temurin)
- [AdoptOpenJDK](#adoptopenjdk)
- [Azul Zulu](#azul-zulu)
- [BellSoft Liberica JDK](#bellsoft-liberica-jdk)
- [IBM Semeru Runtime](#ibm-semeru-runtime)
- [Amazon Corretto](#amazon-corretto)
- [Microsoft Build of OpenJDK](#microsoft-build-of-openjdk)
- [Alibaba Dragonwell](#alibaba-dragonwell)
- [SapMachine](#sapmachine)
- [Red Hat OpenJDK](#red-hat-openjdk)
- [GraalVM](#graalvm)


### OpenJDK builds by Oracle (jdk.java.net)

[Website](https://jdk.java.net) |
[Releases](https://jdk.java.net) |
Docker Images (n/a)

Oracle provides OpenJDK builds for Linux, macOS and windows in a compressed archive format.

These builds will only be updated for a 6 month period. Updates and security patches will not be available after this short period. This also applies for LTS versions! E.g. the latest OpenJDK 11 build was [11.0.2+9](https://jdk.java.net/archive/) while the current OpenJDK version is [11.0.12+7](https://wiki.openjdk.java.net/display/JDKUpdates/JDK11u).

⛔️ Recommendation: Do not use _OpenJDK builds by Oracle_, particularly if you plan to stick with LTS versions.


### Oracle Java SE Development Kit (JDK)

[Website](https://www.oracle.com/java/) |
[Releases](https://www.oracle.com/java/technologies/downloads/archive/) |
Docker Images (n/a)

Oracle provides a commercial version of the OpenJDK, which are based on the exactly same sources of the OpenJDK: The Oracle Java SE Development Kit (JDK).
Oracle provides updates regular updates and security patches for these builds.

The main issue with these builds is Oracle's licensing policy:

Until version 10 builds were published under the [Oracle Binary Code License Agreement](https://www.oracle.com/de/downloads/licenses/binary-code-license.html), which effectivly allowed the builds to be used for commercial projects.

With version 11 to version 16 builds were published under the [Oracle Technology Network License Agreement for Oracle Java SE](https://www.oracle.com/downloads/licenses/javase-license1.html), **which require a fee-based license for usage in production**.
This is why many new distributions of the OpenJDK have emerged.

Version 17 is published under the [Oracle No-Fee Terms and Conditions (NFTC)](https://www.oracle.com/downloads/licenses/no-fee-license.html), which allows the usage of the builds for running _internal business operations_. Unfortunally, it is not defined, what this means. Is a public website running _internal business operations_?

Also, based on this volatile licensing history, it is not predictable, how future version will be licensed.

⛔️ Recommendation: Do not use _Oracle Java SE Development Kit (JDK)_, unless you know what you are doing.


### Adoptium Eclipse Temurin

[Website](https://adoptium.net) |
[Releases](https://adoptium.net/archive.html) |
[Docker Images](https://hub.docker.com/_/eclipse-temurin/)

Eclipse Adoptium is a top-level project under the Eclipse Foundation, which provides resources and a professional governance model for open source software.
The Adoptium Working Group consists of major companies and organizations that have a strategic interest in the Java technology, including Red Hat, IBM, Microsoft, Azul, and the iJUG. The former AdoptOpenJDK project has moved to Eclipse Adoptium.

The Adoptium OpenJDK builds are called _Eclipse Temurin_ to distinguish to project and the builds.

The Eclipse Temurin builds are high-quality, vendor-neutral, and TCK-tested under a permissive license.

Adoptium states, it will continue to build binaries for LTS releases as long as the corresponding upstream source is actively maintained.

✅ Recommendation: Adoptium Eclipse Temurin OpenJDK builds are highly recommended.


### AdoptOpenJDK

[Website](https://adoptopenjdk.net) |
[Releases](https://adoptopenjdk.net/archive.html?variant=openjdk11&jvmVariant=hotspot) |
[Docker Images](https://hub.docker.com/_/adoptopenjdk)

The AdoptOpenJDK project was the predecessor of Eclipse Adoptium and provided high-quality OpenJDK builds, both for the default HotSpot and the OpenJ9 virtual machine.

The website and older releases are kept online to access archived releases.

⛔️ Recommendation: Do not use _AdoptOpenJDK_ anymore. Use _Adoptium Eclipse Temurin_ OpenJDK builds instead.


### Azul Zulu

[Website](https://www.azul.com) |
[Releases](https://www.azul.com/downloads/?package=jdk#download-openjdk) |
[Docker Images](https://hub.docker.com/r/azul/zulu-openjdk)

Azul Systems, Inc., has specialized in professional Java technologies and commercial support for JDK.
Azul has a high industry reputation and is engaged in various working groups to evolve the Java platform.

Azul provides open source OpenJDK builds called _Azul Zulu_ for many operating systems and architectures.
Additionally, Azul provides builds for special requirements, such as stripped down JREs and builds including OpenJFX.

A downside of these builds is the dependency to a single company, that may suddenly change its license or update policies.

✅ Recommendation: _Azul Zulu Builds of OpenJDK_ are a good choice.

### BellSoft Liberica JDK

[Website](https://bell-sw.com) |
[Releases](https://bell-sw.com/pages/downloads/?) |
[Docker Images](https://hub.docker.com/u/bellsoft)

Similar to Azul, BellSoft has specialized in professional Java technologies and commercial support for JDK.
Also, BellSoft has a high industry reputation and is engaged in various working groups to evolve the Java platform.

BellSoft provides open source OpenJDK builds called _Liberica JDK_ for pretty much all operating systems and architectures.

The popular Spring Boot framework chose Liberica JDK as runtime for their [buildpack](https://github.com/paketo-buildpacks/bellsoft-liberica).

A downside of these builds is the dependency to a single company, that may suddenly change its license or update policies.

✅ Recommendation: _BellSoft Liberica JDK_ builds are a good choice.


### IBM Semeru Runtime

[Website](https://developer.ibm.com/languages/java/semeru-runtimes/) |
[Releases](https://developer.ibm.com/languages/java/semeru-runtimes/downloads/) |
Docker Images (n/a)

IBM developed its own version of the Java Virtual Machine, called J9 and it was open-sourced as _Eclipse OpenJ9_.
It is an alternative to the default HotSpot Java Virtual Machine, but it has never gained much popularity.

IBM now provides builds called _Semeru Runtime_ based on the Eclipse OpenJ9 Java Virtual Machine and some OpenJDK class libraries.

⛔️ Recommendation: There is no reason to use _IBM Semeru Runtime_, unless you know that you need the OpenJ9 Virtual Machine.


### Amazon Corretto

[Website](https://aws.amazon.com/de/corretto/) |
[Releases](https://aws.amazon.com/de/corretto/) |
[Docker Images](https://hub.docker.com/_/amazoncorretto)

Since Oracle changed the support and license policy for its OpenJDK builds, major cloud providers decided to establish their own managed OpenJDK builds and providing long-term updates. Apparantly, this is to avoid risks, especially lawsuits against Oracle.

In 2018, AWS published _Corretto_, yet another OpenJDK build.

AWS includes back ports of bug fixes from newer OpenJDK versions and [claims](https://aws.amazon.com/corretto/faqs/) that they would add patches that might not yet be integrated in the OpenJDK project. Amazon has implemented an alternative [crypto provider](https://github.com/corretto/amazon-corretto-crypto-provider) that has been optimized for their services. It is [planned](https://aws.amazon.com/blogs/opensource/introducing-amazon-corretto-crypto-provider-accp/) to be used as the default crypto implementation in Corretto.

Amazon provides releases for major development platforms and an optimized version for its own Amazon Linux 2.

✅ Recommendation: _Corretto_ builds are a good choice, particularly if you run Java applications directly on Amazon Linux 2 in AWS.


### Microsoft Build of OpenJDK

[Website](https://www.microsoft.com/openjdk) |
[Releases](https://docs.microsoft.com/en-us/java/openjdk/download) |
[Docker Images](https://docs.microsoft.com/en-us/java/openjdk/containers)

In 2021, Microsoft published _Microsoft Build of OpenJDK_, yet another OpenJDK build.

Microsoft may include back ports of bug fixes from newer OpenJDK versions and claims that they would add patches that might not yet be integrated in the OpenJDK project.

Microsoft provides releases for major development platforms.

⚠️ Recommendation: Use _Microsoft Build of OpenJDK_, only if you run Java applications directly on Azure.

### Alibaba Dragonwell

[Website](http://dragonwell-jdk.io) |
[Releases](http://dragonwell-jdk.io) |
[Docker Images](https://github.com/alibaba/dragonwell11/wiki/Use-Dragonwell-11-docker-images)

Alibaba provides an OpenJDK build which includes back ports and some _extra features_.

⛔️ Recommendation: Do not use _Alibaba Dragonwell_, unless you are forced by your government.


### SapMachine

[Website](https://sap.github.io/SapMachine/) |
[Releases](https://github.com/SAP/SapMachine/releases) |
[Docker Images](https://hub.docker.com/_/sapmachine)

SapMachine is yet another OpenJDK Build, maintained by SAP.

⚠️ Recommendation: Use _SapMachine_ only if you are running Java applications on SAP servers.


### Red Hat OpenJDK

[Website](https://developers.redhat.com/products/openjdk/overview) |
[Releases](https://developers.redhat.com/products/openjdk/download) |
[Docker Images](https://catalog.redhat.com/software/containers/ubi8/openjdk-11/5dd6a4b45a13461646f677f4)

Red Had provides OpenJDK builds for LTS versions.

⚠️ Recommendation: Use _Red Hat OpenJDK_ only if you are running Java applications directly on Red Hat Enterprise Linux.


### GraalVM

[Website](https://www.graalvm.org) |
[Releases](https://github.com/graalvm/graalvm-ce-builds/releases) |
[Docker Images](https://github.com/graalvm/container/pkgs/container/graalvm-ce)

GraalVM is a fully compliant JDK, but much different than all the others builds.

GraalVM was developed by Oracle. 
It is based on the OpenJDK but includes a new high-performance compiler and a new polyglot virtual machine (can execute code written in different programming languages).
It is also possible to create platform-specific native executable that are highly optimized and start extremly fast fast.

🤷 Please [share](https://github.com/whichjdk/whichjdk.com/issues/6) your experiences with GraalVM in production, so that we can elaborate a validated recommendation.


## FAQs

### What is the best way to install a JDK for local development?

Use [SDKMAN!](https://sdkman.io/install)

To list available JDKs, type
```
sdk list java
```

and install a specific version:

```
sdk install java 17.0.0-tem
```

Validate by checking the version:

```
java --version
```


### Which version of Java do I currently have installed?

```
which java
`which java` --version
```

On Linux, you might also try
```
sudo update-java-alternatives
```

### What is the difference between JDK and JRE?

Some distributions provide a JDK (Java Development Kit) and a JRE (Java Runtime Environment) build.
A JDK includes everything to _compile, package and run_ Java applications, while a JRE only includes the binaries and libraries to _run_ Java applications.
The JRE is a stripped down version of the JDK, and is smaller in terms of megabytes.

If size matters for you, consider creating your own stripped down runtime using [jlink](https://blog.adoptium.net/2021/10/jlink-to-produce-own-runtime/).

For local development, you need a JDK.
In production you only need a runtime environment, but it is quite common to use the JDK, too.

### What about Java EE?

_Java EE (Java Platform, Enterprise Edition)_ was renamed to _Jakarta EE_.
It is a specification to build server app and frontends.
In terms of scope, Jakarta EE can be compared with more modern frameworks like _[Spring Boot](https://spring.io/projects/spring-boot)_ and _[Quarkus](https://quarkus.io)_, but Jakarta EE feels more complicated.

⚠️ Recommendation: Do not start new projects based on _Jakarta EE_. Use _Spring Boot_ or _Quarkus_.


## About

This site is maintained by [Jochen Christ](https://twitter.com/jochen_christ).
Any recommendations or opinions represented on this site are personal and based on long-term professional experience.
The author is not associated with any of the organizations stated here.

Found an error or something is missing? Please [raise an issue](https://github.com/whichjdk/whichjdk.com/issues/new) or [create a pull request](https://github.com/whichjdk/whichjdk.com/pulls).

Java and OpenJDK are trademarks or registered trademarks of Oracle and/or its affiliates.
