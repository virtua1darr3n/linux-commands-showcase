# awk

## What it does
The `awk` command is used for pattern scanning and processing text, especially for extracting and manipulating structured data.

## Scenario
You need to extract specific columns from logs, analyse structured output, or format command results for easier reading.

---

## Basic usage
```bash
awk '{print $1}' file.txt
```

Prints the first column of each line.

---

## Print multiple columns
```bash
awk '{print $1, $3}' file.txt
```

---

## Print entire line
```bash
awk '{print $0}' file.txt
```

---

## Filter by condition
```bash
awk '/ERROR/ {print $0}' app.log
```

---

## Use with command output
```bash
ps aux | awk '{print $1, $2, $11}'
```

---

## Count lines
```bash
awk 'END {print NR}' file.txt
```

---

## Sum a column
```bash
awk '{sum += $1} END {print sum}' numbers.txt
```

---

## Use custom delimiter
```bash
awk -F: '{print $1}' /etc/passwd
```

---

## Notes
- `$1`, `$2`, `$3` represent columns  
- `$0` represents the entire line  
- `-F` sets the field delimiter  
- `NR` is the number of records (lines)  
- often used for parsing structured data  

---

## Common issue

### Unexpected output
```bash
awk '{print $2}' file.txt
```

### Cause
The file may not be structured as expected (wrong delimiter or spacing).

### Fix
Check file structure:
```bash
cat file.txt
```

Use correct delimiter if needed:
```bash
awk -F: '{print $1}' file.txt
```

---

## Real-world use
- extracting usernames from `/etc/passwd`  
- analysing log files  
- formatting command output  
- summarising data (counts, totals)  

---

## Screenshot

### Extracting columns
![awk columns](/images/awk-columns.png)

### Filtering logs
![awk logs](/images/awk-logs.png)

### Using custom delimiter
![awk delimiter](/images/awk-delimiter.png)

### Processing command output
![awk ps](/images/awk-ps.png)
