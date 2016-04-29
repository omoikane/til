# Restore the correct permissions in `/usr/local`

	sudo chown -R $(whoami):admin /usr/local
	sudo chmod -R g+rwx /usr/local

Or, with [Fish Shell](https://fishshell.com/):

	sudo chown -R (whoami):admin /usr/local
	sudo chmod -R g+rwx /usr/local
