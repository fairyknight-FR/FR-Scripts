import subprocess
import argparse

def run_command(command, output_file):
    try:
        proc = subprocess.Popen(command, stdout=subprocess.PIPE, stderr=subprocess.PIPE, text=True)
        stdout, stderr = proc.communicate()
        with open(output_file, 'a') as f:
            f.write(f"\nCommand: {' '.join(command)}\n")
            f.write(stdout)
            if stderr:
                f.write(f"\nErrors:\n{stderr}\n")
    except Exception as e:
        with open(output_file, 'a') as f:
            f.write(f"\nFailed to run command: {' '.join(command)}\nError: {str(e)}\n")

def main():
    parser = argparse.ArgumentParser(description="Web enumeration using top directory brute-force tools")
    parser.add_argument("-t", "--target", type=str, required=True, help="Target URL or domain")
    parser.add_argument("-o", "--output", type=str, default="web_enum_output.txt", help="Output file to save results")
    args = parser.parse_args()

    target = args.target.rstrip('/')
    output_file = args.output

    banner = """
    **************************************************
    *                  FR-Enum & Dir Brute              *
    **************************************************
    """
    print(banner)
    with open(output_file, 'w') as f:
        f.write(banner)
        f.write(f"\nWeb Enumeration Results for target: {target}\n")
        f.write("="*60 + "\n")

    commands = [
        ["gobuster", "dir", "-u", target, "-w", "/usr/share/wordlists/dirb/common.txt"],
        ["dirb", target, "/usr/share/wordlists/dirb/common.txt"],
        ["wfuzz", "-c", "-w", "/usr/share/wordlists/dirb/common.txt", f"{target}/FUZZ"],
    ]

    for cmd in commands:
        print(f"Running: {' '.join(cmd)}")
        run_command(cmd, output_file)

    print(f"Enumeration complete. Results saved in {output_file}")

if __name__ == "__main__":
    main()
