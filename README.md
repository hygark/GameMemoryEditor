# GameMemoryEditor

nnn2

## Features:

* **Value Search:** Scans the game process memory to find addresses with specific values (e.g., health = 100).
* **Memory Modification:** Changes found values to new ones (e.g., health to 9999).
* **Logging:** Records actions to a file (`memory_editor.log`) and supports sending logs to a webhook (e.g., Discord).
* **CLI Interface:** Simple command-line interaction to specify values to search/modify.
* **Safety Limits:** Restricts the number of found addresses (maximum 100) and includes robust error handling.

## Requirements:

* **C Compiler:** GCC or MSVC (e.g., MinGW for Windows, download from mingw-w64.org).
* **Operating System:** Windows 10/11 (due to the use of `windows.h`).
* **Dependencies:** Standard C library (`windows.h`, included with Windows SDK).
* **Environment Setup:** An emulator such as BlueStacks running Roblox or Free Fire.
* **Libraries:** No external ones required, but `libcurl` may be added for webhook support (optional).

## Installation:

1. **Create a GitHub Repository (optional for versioning):**
   Go to github.com and create a new repository called **"GameMemoryEditor"**.
   Clone the repo to your PC:

   ```bash
   git clone https://github.com/hygark/GameMemoryEditor.git
   ```

2. **Add the Script:**
   Copy the content of `GameMemoryEditor.c` into a C file in your directory.

3. **Compile the Program:**
   In the terminal (with MinGW installed):

   ```bash
   gcc -o GameMemoryEditor GameMemoryEditor.c -lpsapi
   ```

### Configuration in C:

Open the script and edit the definitions at the beginning:

* **PROCESS\_NAME:** Emulator process name (default: `"BlueStacks.exe"`).
* **LOG\_FILE:** Log file name (default: `"memory_editor.log"`).
* **WEBHOOK\_URL:** URL of a Discord webhook (create in Discord > Server Settings > Integrations).
* **SCAN\_INTERVAL:** Interval between scans (default: 100 ms).
* **MAX\_ADDRESSES:** Maximum number of addresses to find (default: 100).
* **VALUE\_TYPE:** Data type to search (default: `int`).

## How to Make It Work?:

1. **Adjust the Configurations:**
   Edit `PROCESS_NAME` to your emulator’s process (e.g., `"BlueStacks.exe"`).

2. **Compile and Run:**

   * Compile:

     ```bash
     gcc -o GameMemoryEditor GameMemoryEditor.c -lpsapi
     ```
   * Run:

     ```bash
     ./GameMemoryEditor
     ```
   * Enter the value to search (e.g., `100` for health) and the new value (e.g., `9999`).

## Testing:

* Open Roblox or Free Fire in an emulator.
* The program scans the memory, lists found addresses, and modifies the values.
* Monitor the console or log file for results (e.g., `"Value modified at 0x12345678 to 9999"`).

**Stopping the Program:**
Close the terminal or press **CTRL+C**.

## Usage Examples:

* **Free Fire Test:** Search for health value (e.g., 100) and modify it to 9999 for testing in a private server.
* **Roblox Test:** Modify coins or resources in a test game (e.g., Pet Simulator, on emulator).
* **Advanced Logging:** Configure a Discord webhook to receive notifications of scans and modifications.
* **Expansion:** Add support for different data types (e.g., `float`) or a GUI with Windows API.

## Legal and Ethical Disclaimer:

This program is for **educational and private testing purposes only**. Do not use it in public games or for cheating, as it may result in bans ().
Always respect the **Terms of Service** of Roblox () and Free Fire.
For ethical pentesting or automation, adapt it for legal scenarios.

