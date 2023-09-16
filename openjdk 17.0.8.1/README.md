# OpenJDK Installation Notes on Ubuntu 22.04.1

1. To ensure the apt libraries are up-to-date:

   `sudo apt update && sudo apt upgrade -y`


2. Install the preferred release of OpenJDK

   `sudo apt-get install openjdk-17-jdk`
  
   
3. To confirm the release of the Java compiler

   `javac -version`
   
   Output: `javac 17.0.8.1`
   
   
4. To confirm the correct release of Java has been installed.

   `java -version`
   
   Output: 
   
   `openjdk version "17.0.8.1" 2023-08-24`
   `OpenJDK Runtime Environment (build 17.0.8.1+1-Ubuntu-0ubuntu122.04)`
   `OpenJDK 64-Bit Server VM (build 17.0.8.1+1-Ubuntu-0ubuntu122.04, mixed mode, sharing)`
