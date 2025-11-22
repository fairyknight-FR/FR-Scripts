# FR-Enum & Dir Brute

A Python script for web directory enumeration using top brute-force tools like Gobuster, Dirb, and Wfuzz with output saved to a file.

## Description

This tool automates web directory brute-force scanning by running multiple popular tools against a target URL or domain. It consolidates results from different enumeration tools into one output file for easy analysis.

## Features

- Supports Gobuster, Dirb, and Wfuzz directory brute-force tools
- Takes target URL or domain as input via command-line switch
- Saves combined output to a user-defined file
- Prints progress and banners for clarity

## Requirements

- Python 3.x
- Installed tools: gobuster, dirb, wfuzz
- Wordlist at `/usr/share/wordlists/dirb/common.txt` (default, can be modified)

## Installation

Install required tools on Debian/Ubuntu-based systems (e.g., Kali Linux):

```bash
sudo apt update
sudo apt install gobuster dirb wfuzz

```
> Ensure the wordlist exists or adjust the script accordingly.
______________
## Usage

- Run the script from the command line with the target URL or domain:
```bash
python3 fr_enum_dir_brute.py -t https://example.com -o output.txt
```
> Arguments:

- `-t` or `--target`: The target URL or domain to scan (required)
- `-o` or `--output`: Filename to save results (optional, default: `web_enum_output.txt`)

## Example
```bash
python3 fr_enum_dir_brute.py -t https://testsite.com -o results.txt

```

This will run all the configured tools against `https://testsite.com` and save outputs to `results.txt`.

## Contribution

Feel free to contribute by submitting issues or pull requests on GitHub.

---




