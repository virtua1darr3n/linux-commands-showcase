# Pipelines

## What it does
Pipelines use the `|` operator to pass the output of one command as input to another command.

## Scenario
You need to filter, search, or manipulate command output to quickly find relevant information during troubleshooting.

## Basic pipeline
```bash
ls -l | less
```

## Filter output with grep
```bash
ps aux | grep nginx
```

## Count results
```bash
ls | wc -l
```

## Sort output
```bash
ls -l | sort
```

## Remove duplicate lines
```bash
cat file.txt | sort | uniq
```

## Combine multiple commands
```bash
ps aux | grep ssh | wc -l
```

## Example output
```text
3
```

## Notes
- `|` sends output from one command to another
- pipelines are read from left to right
- commonly used with `grep`, `sort`, `uniq`, and `wc`
- helps filter large amounts of data quickly

## Common error

### Unexpected results when using grep
```bash
ps aux | grep nginx
```

### Cause
The grep command also matches itself in the output.

### Example
![pipeline grep issue](/images/pipeline-grep-issue.png)

### Fix
Exclude the grep process:

```bash
ps aux | grep nginx | grep -v grep
```

or use a better approach:

```bash
ps aux | grep [n]ginx
```

## Real-world use
- checking running services  
- filtering logs for errors  
- counting active processes  
- cleaning and sorting data  

## Screenshot

### Filtering processes
![pipeline ps grep](/images/pipeline-ps-grep.png)

### Counting files
![pipeline wc](/images/pipeline-wc.png)
