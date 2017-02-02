# Where is `my.cnf` located on Mac OS X?

From [this thread](https://forums.mysql.com/read.php?11,366143,376017#msg-376017) on the MySQL forum:

> By default, the OS X installation does not use a my.cnf, and MySQL just uses the default values.
> To set up your own my.cnf, you could just create a file straight in /etc.

So, copy the example configuration file `my-huge.cnf` in `/etc`:

```
sudo cp /usr/local/mysql/support-files/my-huge.cnf /etc/my.cnf
```

Edit the file (`sudo nano /etc/my.cnf`) and restart the MySQL server.
