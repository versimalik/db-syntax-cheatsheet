# Database Syntax Cheatsheet


## login ke mysql
```sh
mysql -u root -p
```

> sesuikan dengan user pada sistem

---
## membuat database
```sql
CREATE DATABASE nama_database;
```
---
## memilih database
```sql
USE nama_database;
```
---
## membuat table
```sql
CREATE TABLE nama_table(
    column data_type constraint,
    column data_type constraint,
    column data_type constraint,
    . . . . . 
    PRIMARY KEY (column)   
);
```
---
## menambahkan constraint foreign key untuk table yang sudah jadi
```sql
ALTER TABLE nama_table_child
ADD CONSTRAINT nama_foreign_key
FOREIGN KEY(column_table_child)
REFERENCES nama_table_parent (column_table_parent)
ON UPDATE CASCADE
ON DELETE NO ACTION
;
```