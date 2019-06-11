# SQL Style Guide

Consistent code style has many benefits.  Use this guide to keep SQL code neat, tidy and maintainable.

## Basics

* tabs set to two spaces
* everything is **lowercase** - syntax highlighting is the job of the text editor / IDE
* `where` always coded as `where 1=1`
* `select`, `from`, `where 1=1`, `group by`, `order by`, `having` on their own lines and preceded by a blank line
* prefer listing fields than uisng `*`
* use aliases even when there is only one table in the query - this makes joining more tables at a later time easier
* single line queries only allowed where only one field is in `select` statement, no joins and only one condition in `where` statement.
* fields in select statement as below

```sql
-- This is a basic SQL query

select
   x.col1   -- Three spaces (tab + space) for first field in select.  This allows alignment of fields.
  ,x.col2
  ,x.col3

from table_x x

where 1=1
  and x.col3 = 'condition one'
;

-- single line query

select col1 from table_x where col3 'condition one'
;
```

## Joins

* SQL92 rather than SQL89 joins
* Prefer condensed verbs, eg. `left join` rather than `left outer join`
* join statements on their own line preceded by a blank line
* left hand side of join condition should correspond to left hand table in join
* `on` / `and` as below

```sql
-- This is a basic SQL query with several joins

select
   x.col1   -- Three spaces (tab + space) for first field in select.  This allows alignment of fields.
  ,x.col2
  ,x.col3

from table_x x

inner join table_y y
  on x.col1 = y.col1

left join table_z z
  on x.col2 = z.col2

where 1=1
  and x.col3 = 'condition one'
```

## Subqueries / Common Table Expressions

* avoid subqueries
* use Common Table Expressions (CTEs) instead
* even better - use staging tables (ie. multiple `create table` statements
