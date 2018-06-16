# SQLite3 
SQLite provides a embedded simple and fast 
(2x faster than PostgreSQL or MySQL) SQL database. 
See http://www.hwaci.com/sw/sqlite/ for details. 
It's SQL command set is described 
at http://www.hwaci.com/sw/sqlite/lang.html. 
SQLite was written by Dr. Richard Hipp who offers consulting 
services for custom modifications and support of SQLite. 

Example:

```Io
db := SQLite clone
db setPath("myDatabase.sqlite")
db open
db exec("CREATE TABLE Dbm (key, value)")
db exec("CREATE INDEX DbmIndex ON Dbm (key)")
db exec("INSERT INTO Dbm ('key', 'value') VALUES ('a', '123')")
db exec("INSERT INTO Dbm ('key', 'value') VALUES ('a', 'efg')")
rows := db exec("SELECT key, value FROM Dbm WHERE key='a'")
db exec("DELETE FROM Dbm WHERE key='a'")
rows := db exec("SELECT key, value FROM Dbm WHERE key='a'")
db close
```

# Installation
SQLite should be installed and foundable in your system. Then:
```
eerie install https://github.com/IoLanguage/SQLite3.git
```
