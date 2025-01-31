Solutions Considered

Reading the Entire File into Memory

This approach loads the entire 1TB log file into memory and processes it.

Issue: Not feasible due to excessive memory consumption.

Using Grep or Similar CLI Tools

Commands like grep "YYYY-MM-DD" test_logs.log > output.txt were considered.

Issue: While fast, this approach depends on system tools and may not be portable across all environments.

Streaming Approach (Line-by-Line Processing)

Reads the file line by line and writes only the relevant logs to the output file.

Advantage: Efficient in terms of memory usage and works well for large files.

Issue: May be slightly slower than some CLI-based solutions but ensures better compatibility and scalability.

Final Solution Summary

The final solution utilizes a streaming approach, where the script reads the log file line by line and extracts only the logs matching the given date. This method ensures low memory usage and efficient processing, making it well-suited for handling a 1TB log file. Additionally, it includes error handling for missing files and other potential issues.

Steps to Run

Ensure Python is installed on your system.

Download the log file using the following command:

curl -L -o test_logs.log "https://limewire.com/d/90794bb3-6831-4e02-8a59-ffc7f3b8b2a3#X1xnzrH5s4H_DKEkT_dfBuUT1mFKZuj4cFWNoMJGX98"

Run the script with the desired date:

python extract_logs.py test_logs.log YYYY-MM-DD

The extracted logs will be saved in the output/ folder with the filename output_YYYY-MM-DD.txt.

Check the output logs in the output/ directory.
