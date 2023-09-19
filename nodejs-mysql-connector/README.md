## Connecting to MySQL database using Node.js on Ubuntu 22.04.1



### Pre-requisite Softwares


1. We must verify that the following necessary softwares are correctly installed. 

    - _nodejs v12.22.9_
    - _MySQL 8.0.34_

    Please refer to the README sections of the respective software packages.
    
    

2. Create a new `Node.js` project under the desired directory and run the following command.

 ```
 npm init
This utility will walk you through creating a package.json file.
It only covers the most common items, and tries to guess sensible defaults.

See `npm help init` for definitive documentation on these fields
and exactly what they do.

Use `npm install <pkg>` afterwards to install a package and
save it as a dependency in the package.json file.

Press ^C at any time to quit.
package name: (foo) 
version: (1.0.0) 
description: 
entry point: (index.js) 
test command: 
git repository: 
keywords: 
author: 
license: (ISC) 
About to write to /media/sandeep/SANDEEP_C/DOCHUB/11_Repositories/01. Github/foo/package.json:

{
  "name": "foo",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC"
}


Is this OK? (yes) yes
``` 


3. Install the `MySQL` Package for `Node.js`

```
npm install mysql

added 11 packages, and audited 12 packages in 6s

found 0 vulnerabilities
```


4. `Node.js` code to connect to `MySQL` database


```
const mysql = require('mysql');

// create a new MySQL connection
const connection = mysql.createConnection({
  host: 'localhost',
  user: 'sandeep',
  password: 'user_password',
  database: 'database_name'
});
// connect to the MySQL database
connection.connect((error) => {
  if (error) {
    console.error('Error connecting to MySQL database:', error);
  } else {
    console.log('Connected to MySQL database!');
  }
});

// close the MySQL connection
connection.end();
```


5. Run `Node.js` and test the connection

```
node Node.js 
Connected to MySQL database!
```
