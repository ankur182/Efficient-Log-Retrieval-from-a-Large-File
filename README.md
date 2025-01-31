## Efficient Log Retrieval from a Large File

📌 Solutions Considered

## 1. Reading the Entire File into Memory

This approach loads the entire 1TB log file into memory and processes it.

 ❌ Issue: Not feasible due to excessive memory consumption.

## 2. Using Grep or Similar CLI Tools

Commands like:

grep "YYYY-MM-DD" test_logs.log > output.txt

✅ Pros: Very fast and simple.

❌ Cons: Not flexible for advanced filtering.

## 3. Using Python with Buffered Reading

Reads the file line by line and writes matching entries to an output file.

📌 Code Implementation

log_file = "test_logs.log"
output_file = "filtered_logs.txt"
search_date = "YYYY-MM-DD"

with open(log_file, "r") as infile, open(output_file, "w") as outfile:
    for line in infile:
        if search_date in line:
            outfile.write(line)

✅ Pros: Efficient, doesn't use too much memory, and allows custom filtering.

❌ Cons: Slightly slower than grep.

## 🎯 Final Solution Summary

We chose Python with buffered reading because it's a simple and efficient way to process large log files without consuming too much memory. It allows us to apply custom filtering while keeping the implementation easy to understand.

🚀 Steps to Run

✅ Prerequisites

Install Python (python3 --version).

Ensure the log file (test_logs.log) is in the same directory.

▶️ Running the Script

Update search_date in log_filter.py with the required date.

Run the script:

python3 log_filter.py

The filtered logs will be saved in filtered_logs.txt.
