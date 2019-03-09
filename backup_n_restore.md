### backup

```
cd frappe-bench
bench restore --with-files
```


### restore

#### on your target server

if you have an existing instance

1. login to mysql
`mysql -u root -p -h localhost`

2. identify the database name
`SHOW DATABASES;`

3. drop existing database
`DROP DATABASE [db_name];`

