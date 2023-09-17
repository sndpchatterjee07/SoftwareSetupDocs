#  Apache Tomcat 10.1.13 Installation Notes on Ubuntu 22.04.1

1. Download the binary distribution of Apache Tomcat 10.1.13 from `https://tomcat.apache.org/download-10.cgi`

   `https://dlcdn.apache.org/tomcat/tomcat-10/v10.1.13/bin/apache-tomcat-10.1.13.tar.gz`


2. Extract it to an appropriate folder and run the server using **./startup.sh** from **bin** directory.

   ```
   sandeep@sandeep-Inspiron-3493:~/Downloads/apache-tomcat-10.1.13$ cd bin/
   sandeep@sandeep-Inspiron-3493:~/Downloads/apache-tomcat-10.1.13/bin$ ./startup.sh
   Using CATALINA_BASE:   /home/sandeep/Downloads/apache-tomcat-10.1.13
   Using CATALINA_HOME:   /home/sandeep/Downloads/apache-tomcat-10.1.13
   Using CATALINA_TMPDIR: /home/sandeep/Downloads/apache-tomcat-10.1.13/temp
   Using JRE_HOME:        /usr
   Using CLASSPATH:       /home/sandeep/Downloads/apache-tomcat-10.1.13/bin/bootstrap.jar:/home/sandeep/Downloads/apache-tomcat-10.1.13/bin/tomcat-juli.jar
   Using CATALINA_OPTS: 
   Tomcat started.
   ```
