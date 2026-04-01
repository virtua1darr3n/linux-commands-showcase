# wc

## What it does
The `wc` (word count) command is used to count lines, words, and characters in files or command output.

## Scenario
You need to count log entries, measure file size in terms of lines, or analyse output from other commands.

---

## Count lines
```bash
wc -l file.txt
```

---

## Count words
```bash
wc -w file.txt
```

---

## Count characters
```bash
wc -c file.txt
```

---

## Count all (lines, words, characters)
```bash
wc file.txt
```

---

## Use with pipelines

### Count number of files
```bash
ls | wc -l
```

---

### Count matching lines
```bash
grep "ERROR" app.log | wc -l
```

---

## Example output
```text
5 file.txt
```

---

## Notes
- `-l` counts lines  
- `-w` counts words  
- `-c` counts characters  
- commonly used with pipelines for quick analysis  

---

## Common issue

### Unexpected count
```bash
ls | wc -l
```

### Cause
Hidden files are not included.

### Fix
Include hidden files:
```bash
ls -a | wc -l
```

---

## Real-world use
- counting log entries  
- checking number of files in a directory  
- analysing output from commands  
- measuring file content size  

---

## Screenshot

### Counting lines
![wc lines](/images/wc-lines.png)

### Counting words
![wc words](/images/wc-words.png)

### Using wc with grep
![wc grep](/images/wc-grep.png)
