#  dbwrapper 

dbwrapper is a small php wrapper for mysql databases.

## installation

install once with composer:

```
composer require dokakoka/db-wrapper
```

then add this to your project:

```php
require __DIR__ . '/vendor/autoload.php';
use dokakoka\DbWrapper\db;
$db = new db();
```

## usage

```php
/* connect to database */
$db = new db('127.0.0.1', 'username', 'password', 'database', 3306);

/* insert/update/delete */
$id = $db->insert('tablename', ['col1' => 'foo'])->excute();
$db->update('tablename', ['col1' => 'bar'], ['id' => $id])->excute();
$db->delete('tablename', ['id' => $id])->excute();

/* select */
$db->select("*", 'tablename', ['id' => $id]);

```