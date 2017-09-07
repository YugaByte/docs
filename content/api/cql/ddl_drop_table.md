---
title: DROP TABLE
summary: Remove a table
---
<style>
table {
  float: left;
}
#psyn {
  text-indent: 50px;
}
#ptodo {
  color: red
}
</style>

## Synopsis
`DROP TABLE` command is to remove a table and all of its data from the database. For example, the following command drops the table "yugatab".
<p id=psyn>`DROP TABLE yugatab;`</p>

## Syntax
drop_table::=
<p id=psyn><code>
   DROP TABLE [ IF EXISTS ] table_name;
</code></p>

Where<br>
  <li>`table_name` is an identifier.</li>
</p>


## Semantics

<li>An error is raised if the specified `table_name` does not exist unless `IF EXISTS` option is present.</li>
<li>Associated objects to `table_name` such as prepared statements will be eventually invalidated after the drop statement is completed.</li>

## Examples

cqlsh>`CREATE TABLE yugatab(name text, id int primary key);`<br>

cqlsh>`DROP TABLE yugatab;`<br>

## See Also

[`ALTER TABLE`](../ddl_alter_table)
[`CREATE TABLE`](../ddl_create_table)
[`DELETE`](../dml_delete)
[`INSERT`](../dml_insert)
[`SELECT`](../dml_select)
[`UPDATE`](../dml_update)
[Other SQL Statements](..)