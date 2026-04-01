# tee

## What it does
The `tee` command reads input and writes it to both the terminal and a file at the same time.

## Scenario
You want to save command output to a file while still seeing it on the screen, such as logging results or capturing command output during troubleshooting.

---

## Write output to a file
```bash
echo "Hello world" | tee file.txt
```

---

## Append to a file
```bash
echo "Another line" | tee -a file.txt
```

---

## Use with pipelines

### Save command output
```bash
ls -l | tee output.txt
```

---

### Save and filter logs
```bash
grep "ERROR" app.log | tee errors.txt
```

---

## Example output
```text
Hello world
```

(File will also contain the same output)

---

## Notes
- `tee` writes output to both terminal and file  
- `-a` appends instead of overwriting  
- commonly used in pipelines  
- useful for logging command output  

---

## Common issue

### File overwritten unexpectedly
```bash
echo "test" | tee file.txt
```

### Cause
`tee` overwrites the file by default.

### Fix
Use append mode:
```bash
echo "test" | tee -a file.txt
```

---

## Real-world use
- logging command output  
- saving filtered logs  
- debugging scripts  
- capturing results while monitoring output  

---

## Screenshot

### Writing to file
![tee basic](/images/tee-basic.png)

### Appending to file
![tee append](/images/tee-append.png)

### Using tee with grep
![tee grep](/images/tee-grep.png)
