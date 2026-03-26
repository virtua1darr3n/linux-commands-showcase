# Creating Files and Directories

## What it does
Linux provides commands such as `mkdir` and `touch` to create directories and files.

## Scenario
You are setting up a project, script, or service and need to create directories for logs, scripts, and configuration files.

## Create a directory
```bash
mkdir logs
```

## Create multiple directories
```bash
mkdir scripts backups
```

## Create nested directories
```bash
mkdir -p /home/darren/projects/app/logs
```

## Create a file
```bash
touch app.log
```

## Create multiple files
```bash
touch file1.txt file2.txt file3.txt
```

## Verify creation
```bash
ls -l
```

## Notes
- `mkdir` creates directories
- `mkdir -p` creates parent directories if they do not exist
- `touch` creates empty files or updates timestamps
- always verify using `ls` or `tree` if available

## Real-world use
Used when setting up applications, creating log directories, preparing scripts, or organising project files.

## Screenshot

### Creating directories and files
![creating files and directories](/images/mkdir-touch.png)

### Nested directory creation
![mkdir nested](/images/mkdir-p.png)
