# MongoDB v6.0.10 Installation Notes on Ubuntu 22.04



1. To ensure the apt libraries are up-to-date & install the necessary packages:

    ```
     sudo apt update && sudo apt upgrade -y
     sudo apt install wget curl gnupg2 software-properties-common apt-transport-https ca-certificates lsb-release`
    ```



2. Import the public GPG key for MongoDB    

   ```
   curl -fsSL https://www.mongodb.org/static/pgp/server-6.0.asc|sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/mongodb-6.gpg
   ```


3. Add the repository

  ```	
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu $(lsb_release -cs)/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list
  ```
  


4. Install MongoDB 6.0 on Ubuntu 22.04 
  
   `sudo apt install mongodb-org`
   
   
   
   
5. Verify MongoDB installed version

   `mongod -version`
   
   
   **Output:**
  
   ```
   db version v6.0.10
   Build Info: {
    "version": "6.0.10",
    "gitVersion": "8e4b5670df9b9fe814e57cb5f3f8ee9407237b5a",
    "openSSLVersion": "OpenSSL 3.0.2 15 Mar 2022",
    "modules": [],
    "allocator": "tcmalloc",
    "environment": {
    "distmod": "ubuntu2204",
    "distarch": "x86_64",
    "target_arch": "x86_64"
  }
}

```
  

6. Start and enable MongoDB

   `sudo systemctl enable --now mongod`	

   **Output:**
   
   `Created symlink /etc/systemd/system/multi-user.target.wants/mongod.service → /lib/systemd/system/mongod.service.`
   
   
   
 7. Verify MongoDB Status


	`systemctl status mongod`
    
  
   **Output:**
   
   ```
   mongod.service - MongoDB Database Server
     Loaded: loaded (/lib/systemd/system/mongod.service; enabled; vendor preset: enabled)
     Active: active (running) since Tue 2023-09-19 23:47:39 IST; 2min 32s ago
       Docs: https://docs.mongodb.org/manual
   Main PID: 24005 (mongod)
     Memory: 68.0M
        CPU: 1.022s
     CGroup: /system.slice/mongod.service
             └─24005 /usr/bin/mongod --config /etc/mongod.conf

   Sep 19 23:47:39 sandeep-Inspiron-3493 systemd[1]: Started MongoDB Database Server.
   ```


8. Configure MongoDB

   MongoDB's configuration file may be found at `/etc/mongod.conf`. 
   The database path, logs directory, and any other necessary configurations can be made in this file. 

    

9. Enable Password Authentication

   When this is enabled, users must enter a password in order to read and edit databases. Uncomment the following line on the above file `/etc/mongod.conf` to do this:

```
security:
  authorization: enabled
```



10. Set the following to bind to every IPv4 and IPv6 address


 	bindIp: 0.0.0.0
 
 
11. After making the above/necessary modifications mentioned in step 9 and 10, save the file, and then restart the service 

		sudo systemctl restart mongod
    