# Laboratory 09 – The Cloud Automation Engineer

## Mission Overview

This laboratory explores Linux automation using Bash scripts and cron jobs. The activity demonstrates how repetitive cloud administration tasks, such as backing up important application data, can be automated.

## Objectives

- Understand Bash scripts, variables, and cron jobs.
- Create a script that backs up application data.
- Apply executable permissions to a Bash script.
- Schedule an automated backup using cron.
- Document the commands, results, and lessons learned.

## Commands Executed

```bash
mkdir app-data
echo "This is critical client data." > app-data/data.txt
nano backup.sh
chmod +x backup.sh
./backup.sh
ls -l backups/
crontab -l
env EDITOR=nano crontab -e
```

## Skills Learned

- Bash scripting and variables
- Linux file permissions
- Data compression using `tar`
- Scheduling automated tasks with cron
- Backup verification and documentation
