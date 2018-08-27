### Backup Database
##### pg_dump is the PostgreSQL utility to backup the database.

##### To backup a single database, run below command in command line interface as superuser.
```
~ sudo pg_dump -U postgres -h localhost name-of-database > name-of-backup-file
```

### Restore Database
```
 sudo su - postgres
 postgres@usr-Aspire-E5-575G:~$ psql
 postgres=# CREATE DATABASE new_database_name TEMPLATE template0;
 postgres@usr-Aspire-E5-575G:~$ psql new_database_name < /home/siv/name-of-backup-file
```
