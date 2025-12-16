# AutoCompiler Script - zim

**Author: Emanuel Abizimi**

## Description

`ZIM` is a Bash script designed to monitor changes to a specific file and automatically restart the compilation or execution process using the specified compiler or interpreter. This tool is useful for developers working in languages like PHP, Python, or others, where source files need to be frequently reloaded.

---

## Features

- Continuous monitoring of changes to a given file.
- Automatic restart of the process when the file is updated.
- Supports any compiler or interpreter (e.g., PHP, Python, etc.).
- Error handling in case of non-existent files or incorrect arguments.

---

## Prerequisites

- Linux or macOS operating system with Bash.
- Access to an interpreter or compiler for the target language (e.g., PHP 8, Python 3, etc.).

---

## Installation

1. Download the script and ensure it is executable:
   ```bash
   chmod +x zim



### Code Structure

The script is structured to perform several essential tasks to monitor a file and restart a compilation or execution process when the file is modified. Here are the main sections of the script:

- Argument Validation:
        Validates the arguments provided when running the script.
        Ensures that the correct parameters are passed for the source file and compiler/interpreter.

- Modification Monitoring:
        Uses the stat command to check changes in the file’s modification date.
        Allows detection of changes in the source file to determine whether the process needs to be restarted.

 - Process Management:
        Launches the compiler or interpreter for the specified file, for example by running php8 or python3 depending on the provided argument.
        If a modification is detected, the current process is restarted to use the updated version of the file.

- Infinite Loop:
     The script continues to monitor the file in an infinite loop.
     It performs checks every second (by default) to detect any changes.

### Limitations

Although this script is useful in many cases, it has certain limitations:

- Compatibility:
        The script uses Linux/macOS-specific commands like stat and kill, which may limit its compatibility with systems like Windows.
- Unmanaged Complex Cases:
        The script does not handle complex cases such as multiple file dependencies or files included within the monitored file.

### Contribution

Contributions are welcome! If you find bugs or would like to add features, feel free to:

Submit a pull request
Open an issue

We encourage users to improve the script by suggesting improvements or bug fixes.
License

This project is distributed under the MIT license.


