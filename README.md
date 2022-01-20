# MySQL Database Syntax Cheatsheet


## login ke mysql
```sh
mysql -u root -p
```
> :memo: sesuikan dengan user pada sistem
---

## melihat daftar database dalam database server
```sql
SHOW DATABASES;
```
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
## melihat daftar table dalam database
```sql
SHOW TABLES;
```
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
## melihat deskripsi atau struktur table yang sudah dibuat
```sql
DESC nama_table;
```
---
## menambahkan constraint foreign key untuk table yang sudah jadi
```sql
ALTER TABLE nama_table_child
ADD CONSTRAINT fk_tableChild_columnChild
FOREIGN KEY(column_table_child)
REFERENCES nama_table_parent (column_table_parent)
ON UPDATE CASCADE
ON DELETE NO ACTION
;
```
---
## menampilkan seluruh freign key yang sudah dibuat beserta keterangannya
```sql
SELECT 
  TABLE_NAME AS `Nama Table`,
  COLUMN_NAME AS `Nama Column`,
  CONSTRAINT_NAME AS `Nama Constraint`
  REFERENCED_TABLE_NAME AS `Table Sumber`
  REFERENCED_COLUMN_NAME AS `Column Sumber`
FROM
  INFORMATION_SCHEMA.KEY_COLUMN_USAGE
WHERE
  REFERENCED_TABLE_SCHEMA = nama_database;
```
