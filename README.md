#Folder Locker
A simple batch script to lock and unlock a folder in Windows.

#How it works
The script starts by checking if the folder named "Control Panel.{21EC2020-3AEA-1069-A2DD-08002B30309D}" exists. If it does, the script jumps to the UNLOCK label and prompts the user to enter the password to unlock the folder. If the folder does not exist, the script checks if a folder named "secured" exists. If it does, the script prompts the user to confirm if they want to lock the folder. If the folder does not exist, the script creates a new folder named "secured".

The script uses the following attributes to lock the folder: +h (hidden), +s (system), +r (read-only), +i (not content indexed). When the folder is unlocked, these attributes are removed and the folder is renamed back to "secured".

#How to use
Save the code to a .bat file.
Set the password by replacing secret_password with your desired password.
Run the .bat file as administrator.
Follow the prompt to lock or unlock the folder.
Note
This is a basic folder locking script and should not be relied upon for complete security. There are more secure methods to protect sensitive information.
