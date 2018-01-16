### See Connected Users

#### Run the following from a mysql tool to view all currently running processes (including sleeping connections):
```sql
SHOW PROCESSLIST
```
#### Or, you can query the information_schema table to get the same:
```sql
select * from information_schema.processlist
```
