# Backup Script Guide

## 1. Overview

The backup script automates the process of creating a compressed backup of the `app-data` directory. It uses Bash commands to create a backup folder, generate a timestamp, and save the data as a `.tar.gz` archive.

## 2. Backup Script

```bash
#!/bin/bash
# Automated Backup Script for CloudNova Technologies

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

# Create the backup directory if it does not exist
mkdir -p "$BACKUP_DIR"

# Compress the source directory into a tarball (.tar.gz)
tar -czf "$BACKUP_DIR/backup_$TIMESTAMP.tar.gz" "$SOURCE_DIR"

echo "Backup completed successfully at $TIMESTAMP!"
```

## 3. Making the Script Executable

The command below gives the script permission to run as a program:

```bash
chmod +x backup.sh
```

Without the required execute permission, running `./backup.sh` may produce a `Permission denied` error.

## 4. Scheduling with Cron

The following cron entry schedules the backup script to run every day at 2:00 AM:

```bash
0 2 * * * /root/backup.sh
```

The five fields represent:

| Field | Value | Meaning |
|---|---|---|
| Minute | `0` | At minute zero |
| Hour | `2` | At 2 AM |
| Day of Month | `*` | Every day of the month |
| Month | `*` | Every month |
| Day of Week | `*` | Every day of the week |

The final part, `/root/backup.sh`, is the absolute path to the script. It must match the actual location of `backup.sh`.

## 5. Verification Commands

```bash
./backup.sh
ls -l backups/
crontab -l
```

These commands run the backup script, list the generated backup archives, and display the configured cron jobs.

## 6. Skills Learned

This activity demonstrates how Bash scripts automate repetitive Linux tasks, how file permissions allow scripts to execute, how compressed archives preserve data, and how cron schedules tasks without requiring manual execution.
