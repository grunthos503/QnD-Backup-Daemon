# QnD-Backup-Daemon
A Quick and Dirty Backup Script/Daemon for rsync

This is a rather set of simple scripts to quickly replicate one host to another using rsync over ssh. The script is designed to be run in daemon mode normally, but it also has some flags for debugging or running as a one-off command. Whatever suit's my needs.

To configure the script for daemon mode, set the following variables at the top of the script:

```bash
## User Configurable
local=0
source_directory='/mnt/path/to/source/'
destination_directory='/mnt/path/to/destination/'
destination_host='backup00'
destination_user='netbackup'
```

Toggling local mode is my lazy way of turnign off the ssh option to copy from one local directory to another instead. In local mode, host and user options are ignored. Otherwise, user and host specify the ssh credentials for the destination to backup to, while the destination directory is a folder on that host.

### Command Options

```
Usage: qnd-rsync-backup [OPTIONS]...
The Quick and Dirty Backup Tool

  -c HOSTNAME     Destination computer hostname
  -d DESTINATION  Destination directory path
  -h              Display help
  -l              Toggle local backup mode
  -s SOURCE       Source directory path
  -u USERNAME     Destination user name
  -v              Display verbose
```
