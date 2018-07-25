# SQLite 基本使用


## Database & Table

- 创建数据库 `create database dbname`
- 删除数据库 `drop database dbname`
- 创建表 `create table tbname if not exist ...`
- 删除表 `drop table tbname`

## 增删查改

- 增 `insert into tbname (field1, field2) values (value1, value2)`
- 删 
    - 删除所有数据 `delete from tbname`
    - 条件删除 `delete from tbname where ...`
- 查 
    - `select * from tbname` 查找所有
    - `select * from tbname where field=value` 条件查找
    - `select * from field like '%value%'` 模糊查找
- 改 `update tbname set field1=value1, field2=value2 where ...`
