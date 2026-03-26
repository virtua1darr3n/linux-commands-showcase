# locate

## What it does
The `locate` command is used to quickly find files and directories by name using a pre-built database.

## Scenario
You need to quickly find the location of a file or configuration without searching the entire filesystem manually.

## Basic usage
```bash
locate file.txt
```

## Search for a file
```bash
locate nginx.conf
```

## Case-insensitive search
```bash
locate -i nginx
```

## Limit number of results
```bash
locate -n 5 nginx
```

## Example output
```text
/etc/nginx/nginx.conf
/usr/share/nginx/html/index.html
```

## Notes
- `locate` is faster than `find` because it uses a database
- results may be outdated if the database has not been updated
- use `updatedb` to refresh the database (may require sudo)

## Update database
```bash
sudo updatedb
```

## Common error

### Error message
```bash
locate: command not found
```

### Cause
The `locate` package is not installed on the system.

### Fix
Install it using:

```bash
sudo apt install plocate
```

Then update the database:

```bash
sudo updatedb
```

## Real-world use
- quickly locating configuration files (e.g. nginx, ssh, system services)  
- finding files without scanning the entire system  
- speeding up troubleshooting when file paths are unknown  

## Screenshot

### Searching for files
![locate basic](/images/locate-basic.png)

### Case-insensitive search
![locate ignore case](/images/locate-i.png)
