# Apache Maven 3.6.3 Installation Notes on Ubuntu 22.04.1

1. To ensure the apt libraries are up-to-date:

   `sudo apt update && sudo apt upgrade -y`


2. Install the preferred release of Apache Maven

   `sudo apt-get -y install maven`
  
   
3. To confirm the Apache Maven version

   `mvn -version`
   
   **Output:** 
   
   - `Apache Maven 3.6.3`
   - `Maven home: /usr/share/maven`
   - `Java version: 17.0.8.1, vendor: Private Build, runtime: /usr/lib/jvm/java-17-openjdk-amd64`
   - `Default locale: en_IN, platform encoding: UTF-8`
   - `OS name: "linux", version: "6.2.0-32-generic", arch: "amd64", family: "unix"`
