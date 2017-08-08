# SQL Style Guide

Consistent code style has many benefits.  Use this guide to keep SQL code neat, tidy and maintainable.

## Basics

* tabs set to two spaces
* everything is **lowercase** - save your pinkies!!
* `where` always coded as `where 1=1`
* `select`, `from`, `where 1=1`, `group by`, `order by`, `having` on their own line
* prefer listing fields than uisng `*`
* fields in select statement as below

```sql
select
   col1
  ,col2
  ,col3

from table_x

where 1=1
  and col3 = 'condition one'
```
