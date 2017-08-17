[![Build Status](https://travis-ci.org/JosefFriedrich-shell/rsync-backup.sh.svg?branch=master)](https://travis-ci.org/JosefFriedrich-shell/rsync-backup.sh)

# rsync-backup.sh

## Usage

```
Usage: rsync-backup [-abBdehlLmn] <source> <destination>

DESCRIPTION
	A wrapper command for rsync with the main features:
		- Backups in in the folder '.rsync-backup/backups'
		- Logging per e mail.
		- Source und destination folder checks over scp.

OPTIONS
	-a <path>: Creates a .rsync-backup/please-sync affirmation file for the given folder.
	-b: Beep.
	-B: Backup.
	-d: Delete all log file in the log folder.
	-e: Show execution log.
	-h: Show help.
	-l: Show log summary.
	-L: Show log folder.
	-m: Send logs per mail.
	-n: Send NSCA message to nagios.

LOG FILES
	GENERAL LOG FILE
		/home/jf/rsync-backup-logs/summary.log
		/home/jf/rsync-backup-logs/execution.log

	LOG FILE PER DATE, SOURCE AND DESTINATION
		Directory: /home/jf/rsync-backup-logs
		Naming convention: log_$DATE_$HOSTNAME_$SOURCE_$DESTINATION.log

EXCLUDES
	To exclude some files or folders place a 'excludes' file in the destination
	folder (.rsync-backup/excludes). For further informations read the
	'--exclude-from' section in the 'rsync' manual.

AFFIRMATION_FILE
	Synchronization only works, if in both folders (source and destination) a
	affirmation file exists (.rsync-backup/please-sync).

CONFIGURATION
	Custom configurations can be done in /etc/rsync-backup.conf.

DEPENDENCIES
	- rsync
	- scp
	- tee
```

## Testing

```
make test
```
