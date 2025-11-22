# FR Enum&Dir Brute Script

## Instructions for Using FR Enum&Dir Brute Script

### 1. Prerequisites:

- Ensure you have Python 3 installed on your system.

- Install the directory brute-force tools Gobuster, Dirb, and Wfuzz.

- Have a suitable wordlist such as /usr/share/wordlists/dirb/common.txt available on your machine.

______________

### 2. Installing Required Tools (on Kali/Debian/Ubuntu):

```bash
sudo apt update
sudo apt install gobuster dirb wfuzz
```

_____________

### 3. Download or Clone the Script:

- Download the `fr_enum_dir_brute.py` script from your GitHub repository or clone the repo:

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```
_____________

### 4. Run the Script:

- Use the command line to run the script with the target URL or domain:

```bash
python3 fr_enum_dir_brute.py -t https://targetwebsite.com -o outputfile.txt
```

- `-t` or `--target` is mandatory: specify the URL or domain for enumeration.
- `-o` or `--output` is optional: specify the filename for saving results (default is `web_enum_output.txt`).

_____________

### 5. View Results:

- The script runs Gobuster, Dirb, and Wfuzz directory brute-force scans.

- All output from these tools will be appended to the specified output file.

- Check this file after the scan completes to review the discovered directories.

_____________

### 6. Customization:

- Modify wordlist paths or add additional tools by editing the script if needed.

_______________

### 7. Contribution and Issues:

- Feel free to contribute improvements or report issues via the GitHub repository's issue tracker.

---
