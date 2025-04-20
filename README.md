Deprecated: Use https://github.com/Josef-Friedrich/rsync-watch instead

# rsync-backup.sh


## Summary / Short description

> A wrapper script for rsync with source und destination accessibility checks, advanced logging and backup support.

## Usage

```
Usage: rsync-backup [-abBdehlLmn] <source> <destination>

A wrapper script for rsync with source und destination accessibility checks, advanced logging and backup support.

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

## Project pages

* https://github.com/Josef-Friedrich/rsync-backup.sh

## Testing

```
make test
```

