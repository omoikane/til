# Restore the correct permissions in `/usr/local`

**❗️This method is potentially dangerous. Use it at your own risk!**

	sudo chown -R $(whoami):admin /usr/local
	sudo chmod -R g+rwx /usr/local

Or, with [Fish Shell](https://fishshell.com/):

	sudo chown -R (whoami):admin /usr/local
	sudo chmod -R g+rwx /usr/local

### MySQL return `ERROR 1018 (HY000): Can't read dir of '.' (errno: 13)`

Probably you have installed MySQL using the mysql community server dmg installer on mysql.com. In this case you should restore the mysql privileges:

	sudo chown -R mysql:mysql /usr/local/mysql/data/
	sudo chmod -R 755 /usr/local/mysql/data/
