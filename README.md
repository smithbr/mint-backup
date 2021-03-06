# mint-backup

A backup script I made for saving quick and dirty snapshots of my laptop's `/home` and `/opt` directories to Dropbox.

## Setup

		$ git clone git@github.com:smithbr/backup.sh.git
		$ mkdir ~/Dropbox/Backups/mylaptop
		$ cp backup.sh/* ~/Dropbox/Backups/mylaptop
		$ rm -rf backup.sh
		$ cd ~/Dropbox/Backups/mylaptop

## Include/Exclude

Add files and folders to backup to `sources.txt`

Add files and folders to exclude to `exclude.txt`

## Backup

Optional: add an alias to `~/.bashrc`

		$ echo '# backup.sh' >> ~/.bashrc
		$ echo "alias dobackup='cd $HOME/Dropbox/Backups/mylaptop && sh backup.sh'" >> ~/.bashrc

Start backup

		$ source ~/.bashrc
		$ dobackup

## Restore

Restore last backup

		$ cd ~/Dropbox/Backups/mylaptop
		$ sh restore.sh backup.tar.gz myrestore1
		
Or archived backup

		$ cd ~/Dropbox/Backups/mylaptop
		$ sh restore.sh archive/backup-000000000000.tar.gz myrestore1

Explore the restored backup

		$ cd restored/myrestore1
		$ ls
		$ about.txt  home  opt
