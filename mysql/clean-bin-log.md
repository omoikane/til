# Clean bin logs

If you `cd /usr/local/mysql` and notice a lot of `mysql-bin.***` files, maybe you ask "what are these!?".

These files contain all the binary logs that MySQL has generated over time. **Don’t delete them by the OS!**

To delete them, enter in your mysql shell as admin:

```
mysql -h localhost -u root -p
```

Enter the mysql password and you are in the shell.

The commands to run are:

```
mysql> PURGE BINARY LOGS TO 'log_name';
```

or:

```
mysql> PURGE BINARY LOGS BEFORE datetime_expr;
```

To eliminate them all in one go, you can run:

```
PURGE BINARY LOGS BEFORE DATE(NOW());
```

If you don’t need these files, you can keep only the last 10 days (or what you want):

```
mysql> SET GLOBAL expire_logs_days = 10;
```

Then, add this to `/etc/my.cnf` (see [Where is my.cnf located on Mac OS X?](mac-osx-config.md)):

```
[mysqld]
expire_logs_days=10
```

## References

- [PURGE BINARY LOGS Syntax](https://dev.mysql.com/doc/refman/8.0/en/purge-binary-logs.html)
- [Is it safe to delete mysql-bin files?](https://dba.stackexchange.com/a/41054)
