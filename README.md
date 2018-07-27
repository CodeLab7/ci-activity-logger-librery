# Codeigniter Activity Log Library

[![N|CodeLab7](https://avatars0.githubusercontent.com/u/39191324?s=200&v=4)](https://codelab7.com)

Activity Log Library is Codeigniter based Library which can be helpful record Activity on a website and Get Results for reporting

  - Easy to Use
  - Simple Sentences for Add & Retrieve Log
  - Standalone Librery for any kind of website

### Installation

Dillinger requires [Codeigniter](https://codeigniter.com) v3 to run.

- Copy Library into your `/application/library` Folder.
- Import logger.sql into your database.
- You are ready to go

You can create Table as follow
```sql
CREATE TABLE `logger` (  `id` bigint(20) NOT NULL AUTO_INCREMENT,  `created_on` timestamp NOT NULL DEFAULT CURRENT_TIMESTAMP,  `created_by`int(11) NOT NULL,  `type` varchar(255) NOT NULL,  `type_id` bigint(20) NOT NULL,  `token` varchar(255) NOT NULL, `comment` text NOT NULL );

ALTER TABLE `logger`  ADD PRIMARY KEY (`id`);
```

You can change in table fields name,  to alter the following line into a library

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

### Uses
Inclide Librery with this code where you want to use.
```php
$this->load->library('logger');
```

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

Want to contribute? Great! Just pull repo and start work, Submit when you satisfy.
Or You can Join our team at [codelab7](https://codelab7.com)



### Todos

 - Advance Testing
 - Add Other Important Fields

License
----
GPL 3.0

**Free Software, Hell Yeah!**