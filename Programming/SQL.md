

To list all Databases in SQL Server,
```sql
Select * from sys.databases 
```

To exclude in-built DBs in SQL Server,
```sql
Select * from sys.databases WHERE name NOT IN ('master', 'tempdb', 'model', 'msdb'); 
```
