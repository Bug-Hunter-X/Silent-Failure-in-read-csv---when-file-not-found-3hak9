# Silent Failure in read.csv() when file not found
This repository demonstrates a common but easily missed error in R: the silent failure of `read.csv()` when the specified file does not exist. The `bug.r` file shows the problematic code.  The solution, `bugSolution.r`, adds robust error handling to gracefully manage the absence of the file.

**Problem:**
The original code directly calls `read.csv()` without checking for the file's existence.  If the file is not found, the function returns `NULL` without producing an error message. This can lead to cryptic errors later in the code, making debugging difficult.

**Solution:**
The improved code includes error handling that checks if the file exists using `file.exists()`. If the file is not found, it prints an informative error message and optionally stops execution.  Alternative approaches to handle missing files (like providing a default dataset) are also demonstrated.