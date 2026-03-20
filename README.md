# Wi-FI-Password-Recovery
WiFi Password Recovery is a Windows tool available as both a Python script and a standalone EXE. It lists all saved WiFi profiles, lets you select one, and displays full details including the password. It also exports the complete output to a TXT file for easy access.

# Full Explanation (Python Script + EXE Version)
WiFi Password Recovery is a Windows tool designed to extract and display saved WiFi profiles stored on the system. It works in two identical forms:

as a Python script (.py)

as a stand‑alone executable (.exe) created from the same script

Both versions perform exactly the same operations and produce the same output.

# 🐍 Python Script Explanation
The Python script uses the Windows command-line utility netsh to interact with the system’s WiFi configuration. When executed, the script performs the following steps:

1. Retrieve all saved WiFi profiles
It runs:

<pre>netsh wlan show profiles
</pre>

# This command lists every WiFi network previously connected to the system.
The script parses this output and extracts the profile names.

# Display the list to the user
All detected WiFi profiles are shown in a numbered list, allowing the user to easily choose one.

3. Let the user select a WiFi network
The user enters the number corresponding to the desired WiFi profile.

4. Show full WiFi details (including password)
The script runs:

<pre>netsh wlan show profile name="PROFILE_NAME" key=clear</pre>

This command displays:

SSID

Authentication type

Encryption

Connection settings

WiFi password in clear text (Key Content)

The full output is printed directly in the console.

5. Export the result to a TXT file
The script automatically creates a text file named after the selected WiFi network, containing the full command output.

# Example:

<pre>MyHomeWiFi.txt</pre>

# EXE Version Explanation (100% False positive)
The .exe version is generated from the same Python script using tools like PyInstaller.
It behaves exactly like the Python version but offers several advantages:

✔ No Python installation required
Users can run the EXE on any Windows machine without installing Python or dependencies.

✔ Same functionality
The EXE performs the same steps:

Lists saved WiFi profiles

Lets the user choose one

Shows full details including the password

Saves the output to a TXT file

✔ Portable
The EXE can be placed on a USB drive or shared with others who need to recover their own WiFi passwords.

✔ Identical output
Both versions generate the same TXT files and display the same information.

# 🔐 Important Note
This tool is intended only for recovering WiFi passwords on networks you own.
Accessing networks without permission is illegal.
