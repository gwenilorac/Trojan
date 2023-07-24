# trojan
Trojan Malware in Python

## Here's a breakdown of the code:

1. The module imports at the beginning of the code include the following:
- socket: Provides support for communication through sockets.
- subprocess: Enables the execution of system commands.
- threading: Facilitates the simultaneous execution of multiple tasks.
- time: Provides time-related functionalities.
- os: Offers functions for interacting with the operating system.
2. CCIP and CCPORT are variables that store the IP address and port of the remote control
server.
3. The autorun() function is used to copy the Trojan file to the current user's Windows startup
folder, ensuring that the Trojan runs whenever the system is started.
4. The conn(CCIP, CCPORT) function creates a client socket and attempts to establish a
connection with the remote control server. If the connection is successful, the client is
returned. Otherwise, any exceptions are printed on the screen.
5. The cli(client) function is executed in a separate thread and is responsible for receiving
commands from the remote control server and executing them on the system. The while True
loop is used to continuously receive commands. If a special command \\\\:kill is received, the
function returns and the connection is closed. Otherwise, the command is passed to the
cmd(client, data) function in a new thread for execution.
6. The final part of the code is where everything is initiated. The autorun() function is called to
copy the Trojan file to the startup folder. Then, a while True loop is executed, attempting to
connect to the remote control server. If the connection is successfully established, the
cli(client) function is called to handle the received commands. Otherwise, the program waits
for 3 seconds before trying again.

### Terminal
Run pyinstaller -F --clean -w trojan.py to package the Trojan into a single executable file
called "trojan.exe".

### Inserting RAT inside an Image
Convert the jpg or png image to an ICO file and create a .zip archive with SFX options. Enable
"Extract and update files" and "Overwrite all files." Click "Browse" in the "Load SFX icon from the
file" section and select the .ico image. Enter the name of .jpg file and .exe file in the "Setup"
tab. Click "OK" twice.

# The Attack Process

## Attacker Machine Process
Use NetCat to listen for incoming connections.

## Target Machine Process
Execute the exported code ensuring that you enter the correct IP address for the backdoor to function properly on the victim's computer. Establish a shell connection using a Reverse Shell technique.
