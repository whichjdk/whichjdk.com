# Which Version of JDK Should I Use?

There are plenty of Java™ Development Kits (JDK) distributions available.  
Pretty much all of them build on the source code of the [OpenJDK](https://openjdk.java.net).  
The distributions differ in licences, commercial support, supported platforms, and update frequency.

## TL;DR

In most cases, use the latest [Adoptium Eclipse Temurin OpenJDK LTS version](https://adoptium.net/releases.html?variant=openjdk11&jvmVariant=hotspot).  
Your platform architecture most likely is `x64`.  
Install using sdkman (on macOS or Linux) or using the MSI installer (Windows).

## Decision Tree

Use the same JDK for development, CI, and production. 

So, how do you run your services in production?

* I don`t know -> Adoptium 11 
* Kubernetes or Docker -> Adoptium 11 
* Directly on cloud compute instances -> Your cloud vendor`s OpenJDK build
* Lambda/Serverless -> Oracle GraalVM 


## Distributions

| Distribution                     | Licence  | Comment  |
|---|---|---|
| AdoptOpenJDK                     |          | Recommended up to OpenJDK 16. AdoptOpenJDK has been rebranded as Adoptium |
| Adoptium Eclipse Temurin         |          | Recommended for OpenJDK 17 and newer.         |
| Bellsoft Liberica JDK            |          |          | 
| Oracle GraalVM                   |          |          | 
| Oracle Java SE Development Kit   |          |          | 
| jdk.java.net OpenJDK             | gplv2+ce |          |
| Amazon Corretto                  | GPL      | Standard OpenJDK for Amazon Linux 2. LTS releases. |
| Azul Zulu                        |          |          | 
| Microsoft Build of OpenJDK       |          |          | 
| SapMachine                       |          |          | 
| Red Hat OpenJDK                  |          |          | 


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
