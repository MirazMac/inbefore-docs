---
layout: default
title: Installation
nav_order: 2
description: "Just the Docs is a responsive Jekyll theme with built-in search that is easily customizable and hosted on GitHub Pages."
permalink: /installation
has_toc: true
last_modified_date: 2020-04-27T17:54:08+0000
---

# Installation

Installing {{ site.item }} is just some simple tasks. Let's begin.

---

### Creating a Database

First thing you need to do before installing {{ site.item }} is to create a new database on your MySQL server. The database must be created under a MySQL user that has full permissions. If you already know how to do this or have already created one you can skip to the next step. But make sure you have noted the following details:

- Database Name - The one you just created
- MySQL Host - Usually it defaults to 127.0.0.1 or localhost, but if that doesn't work you need to contact your hosting provider.
- MySQL Username - The username of which you've created the database.
- MySQL Password - The password for the MySQL user

![image](https://user-images.githubusercontent.com/13865787/85750814-dac45c80-b72b-11ea-9a49-2c324ba002c6.png)

### Importing the SQL dump
After you've created the database import the SQL file provided with the script, to the database by going to phpMyadmin or any other tools. The SQL file is located at: **Database/inbefore.sql**

![Importing the database via phpMyadmin. Your scenario may vary.](https://user-images.githubusercontent.com/13865787/85751035-0a736480-b72c-11ea-95b1-20792ce05eec.png)

### Uploading Files
After importing the SQL file to the database, unzip the .zip file you downloaded from Codecanyon and upload the contents of **Main Files** folder to your server's root folder (usually called www/public_html or something similar) or a sub-directory. 

![image](https://user-images.githubusercontent.com/13865787/85751492-73f37300-b72c-11ea-8228-df710fb1f934.png)
**Important: Upload what's inside the folder *Main Files*, not the folder itself.**

Shared hosting providers usually have a web based file manager, but you should use something like FileZilla to do the upload as the web based managers can cause various problems fairly often.

### Editing the database config file
After you uploaded InBefore files to your server, locate the database config file at: src/settings/db.php and open the file for editing and provide your database details that you have created earlier and save the file.

```php
<?php
/**
 * Put your database details here after you've imported the SQL file
 *
 * @return array
 */
return [

   // Database host. Usually localhost or 127.0.0.1
   'dbhost' => 'localhost',

   // Database name
  'dbname' => '',

  // Database Username
  'username' => 'root',

  // Database password
  'password' => '',

  // 3306 in most cases
  'dbport' => '3306',

  //DON'T CHANGE THIS
  'prefix' => 'in_',
];
```
