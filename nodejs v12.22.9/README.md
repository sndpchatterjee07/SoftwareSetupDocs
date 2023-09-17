# Node.js Installation Notes on Ubuntu 22.04.1

1. To ensure the apt libraries are up-to-date:

   `sudo apt update && sudo apt upgrade -y`


2. Install the preferred release of Node.js

   `sudo apt install nodejs`
  
   
3. To confirm the installation was successful

   `node -v`
   
   **Output:** `v12.22.9`
   
   
4. Install the Node.js package manager 

   `sudo apt install npm`	
   
   
5. To confirm the installation was successful

   `npm -v`
   
   **Output:** `8.5.1`
   
   
6. To install Express globally

   `sudo npm install -g express`
   
   
7. To check the version of the installed npm package globally   

   `npm list -g`
   
   **Output:** 
   
   ```
   /usr/local/lib
   -- express@4.18.2
	```   
	  
8. To install the Express Application Generator	   

   `sudo npm install express-generator -g`	


9. To test Node.js after installation

   -  Create a file named `app.js` containing the following contents:

   ```
   const http = require('http');
   
   const hostname = '127.0.0.1';
   const port = 3000;
   
   const server = http.createServer((req, res) => {
         res.statusCode = 200;
         res.setHeader('Content-Type', 'text/plain');
         res.end('Hello World');
   });
   
   server.listen(port, hostname, () => {
         console.log(`Server running at http://${hostname}:${port}/`);
   });
   ```

   - Now, run your web server using `node app.js`

   - Visit `http://localhost:3000` and you will see a message saying `"Hello World"`.