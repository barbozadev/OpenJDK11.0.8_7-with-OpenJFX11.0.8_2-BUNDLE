# OpenJDK11.0.8_7-with-OpenJFX1-BUNDLE1.0.8_2

## Introduction

>Both distributions are subject to the GNU General Public License, version 2, with the Classpath Exception. More info: https://openjdk.java.net/legal/gplv2+ce.html

>  As OpenJDK11 no longer includes OpenJFX, I have come to need to create a BUNDLE OF OpenJDK11.0.8_7 with OpenJFX11.0.8_2, for those who want to have OpenJfx installed in OpenJDK itself. 

## Code Samples

>THE SIMPLEST AND FASTEST WAY:

>Open Cygwin en cd to the directory of the project, example: Note that have to be forward slash because is in Cygwin that is a UNIX like bash:
cd C:/HERE

    Run configure:
    bash configure --with-import-modules=C:/FOLDER_OF_THIS_PROJECT/openjfx11-modular-sdk

    Run make:
    make images

>Verify your newly built JDK:

    ./build/*/images/jdk/bin/java -version

>READY. You get the project binaries at: build/windows-x86_64-normal-server-release/images/jdk

## Installation

> As OpenJDK11 no longer includes the OpenJFX announced since JDK8, I have come to need to create a BUNDLE OF OpenJDK11.0.8_7 with OpenJFX11.0.8_2, for those who want to have OpenJfx installed in the same OpenJDK. The package or folder "openjfx-modular-SDK" included in the repository has been built before, this according to the OpenJFX manual, if you want to build the OpenJFX by yourself, follow the steps in the manual: https://wiki.openjdk.java.net/display/OpenJFX/Building+OpenJFX


>REQUIREMENTS: 

>https://openjdk.java.net/groups/build/doc/building.html
 
>To build the project, follow the steps according to the manual, but in this case, in the command step "configure" in the bash you have to add this:
   --with-import-modules=C:/FOLDER_OF_THIS_PROJECT/openjfx11-modular-sdk

>The project folder must be at the top of all the directories in Windows, not Cygwin, example: C:\HERE, if you do them from another path, you will get an error when starting with something like this, in my case:
c1xx: fatal error C1083: Cannot open source file: '../../..c:/cygwin64

>It doesn't matter if you change directory, it will always give you that error, it seems to be some Cygwin user trying to find directories but this is another topic.
So you know that in order to build the project, it must be in C:\HERE "the back slash is because it is in windows"
In my case the compilation was done in Windows 10 with the Visual Studio 2017 toolchain using Cygwin.


>Get the complete source code of this repository:
The project of this repository must be in the Top of the directories in Windows, not Cygwin, example: C:\HERE
   

>THE SIMPLEST AND FASTEST WAY:

>Open Cygwin en cd to the directory of the project, example: Note that have to be forward slash because is in Cygwin that is a UNIX like bash:
cd C:/HERE


    Run configure:
    bash configure --with-import-modules=C:/FOLDER_OF_THIS_PROJECT/openjfx11-modular-sdk


    Run make:
    make images

>Verify your newly built JDK:
./build/*/images/jdk/bin/java -version

>READY. You get the project binaries at: build/windows-x86_64-normal-server-release/images/jdk

>>OPTIONAL:

>If configure fails due to missing dependencies (to either the toolchain, build tools, external libraries or the boot JDK), most of the time it prints a suggestion on how to resolve the situation on your platform. Follow the instructions, and try running bash configure again: https://openjdk.java.net/groups/build/doc/building.html
Example: -with-toolchain-version= --with-jvm-variants= , etc.

>--with-jvm-variants = It can be "server", "client", etc. by default without using this command, the server is created.

>-with-toolchain-version = You have to have Visual Studio Build Tools 2017 for C/C ++ or Visual Studio Community 2017 with the Development Package of C/C ++ or if is your case Visual Studio Professional 2017 with the Development Package of C/C ++ .

    Run configure:
    bash configure --with-jvm-variants=server --with-toolchain-version=2017 --with-boot-jdk=C:/YOUR_CURRENT_OR PREFERED_JAVA_HOME_INSTALLED(Is permited from JDK10) --with-import-modules=C:/FOLDER_OF_THIS_PROJECT/openjfx11-modular-sdk

    
>These settings will be detected automatically, but if you get errors, follow the instructions in the manual: https://openjdk.java.net/groups/build/doc/building.html

    Run make:
    make images

Optional, takes longer:
    make all

   >Run make: For different variants configured before in the "configure" section, normally if there is only one or followed the simple steps, you don't need to add the argument "CONF":
  
> Example:
   make all CONF=windows-x86_64-normal-server-release
  or
  make all CONF=windows-x86_64-normal-client-release
    
>Verify your newly built JDK:
  Run bash:
    ./build/*/images/jdk/bin/java -version

>Run basic tests (To run these tests you must enter an environment variable, either temporary in the bash session or adding it from the "bash_profile" file in Cygwin about the location of the test framework to use as "jtreg" and before the command "configure":
    make run-test-tier1
More info: https://openjdk.java.net/groups/build/doc/building.html

>Both distributions are subject to the GNU General Public License, version 2, with the Classpath Exception. More info: https://openjdk.java.net/legal/gplv2+ce.html

>>>I hope it is helpful to the community!!!