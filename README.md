# Codeigniter Activity Log Library

[![N|CodeLab7](https://avatars0.githubusercontent.com/u/39191324?s=200&v=4)](https://codelab7.com)

Activity Log is a Codeigniter library used to record activity on a website and to fetch the results for reporting purposes. 

  - Is easy to Use
  - Simple syntax for adding and fetching records
  - Standalone library for use on any kind of website

### Installation

Logger requires [Codeigniter](https://codeigniter.com) version 3 to run.

- Copy library (Logger.php) into your `/application/library` folder.
- Import logger.sql into your database (or manually create the table).

To manually create the table run the following command in your MySql command prompt:

```sql
CREATE TABLE `logger` (  `id` bigint(20) NOT NULL AUTO_INCREMENT,  
    `created_on` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP,  
    `created_by`int(11) NOT NULL,  
    `type` varchar(255) NOT NULL,  
    `type_id` bigint(20) NOT NULL,  
    `token` varchar(255) NOT NULL, 
    `comment` text NOT NULL );

ALTER TABLE `logger`  ADD PRIMARY KEY (`id`);
```

You can change the field names in the library by altering the following lines in Logger.php

```php
private $table_fields = array(
    'id'         => 'id', //Value will be Actual table field
    'created_on' => 'created_on',
    'created_by' => 'created_by',
    'type'       => 'type',
    'type_id'    => 'type_id',
    'token'      => 'token',
    'comment'    => 'comment',
  );
```

### Loading
To load the logger library add the following

```php
$this->load->library('logger');
```

### Use 
**Log Activity**
```php
$this->logger
     ->user(1) //Set UserID, who created this  Action
     ->type('post') //Entry type like, Post, Page, Entry
     ->id(1) //Entry ID
     ->token('delete') //Token identify Action
     ->log(); //Add Database Entry
```

**Get Entry**
```php
$this->logger
     ->user(1) //Add Only If you want user specific Entry
     ->type('post') //Add Only If you want type specific Entry
     ->id(1) //Add Only If you want typeID specific Entry
     ->token('delete') //Add Only If you want token specific Entry
     ->get(); //Get All Entry
```

### Development
Want to contribute? Great! Just fork, clone, and start working, submit a pull request when you are ready.
Or You can join our team at [codelab7](https://codelab7.com)

### Todo(s)

 - Advance testing
 - Add other important fields

License
----
GPL 3.0

**Free Software, Hell Yeah!**
