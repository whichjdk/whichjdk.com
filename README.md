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



Java and OpenJDK are trademarks or registered trademarks of Oracle and/or its affiliates.
