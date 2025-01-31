# Efficient Log Retrieval from a Large File

## Solutions Considered

### 1. Reading the Entire File into Memory
This approach loads the entire **1TB log file** into memory and processes it.

- **Issue**: Not feasible due to excessive memory consumption.

### 2. Using Grep or Similar CLI Tools
Commands like:
```sh
grep "YYYY-MM-DD" test_logs.log > output.txt
