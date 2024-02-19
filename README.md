# Delete All Files by Type
Ever converted all your m4a files to mp3 on your Mac, only to find it hard to delete all of the m4a after you're done? Or maybe converted all your keynotes into powerpoints, and find it hard to delete all the .key files leftover? This is a solution! All you need is to make sure Homebrew is installed, and make sure that the tool shc, which we're going to use to compile the executables, is also installed.

Installation:
1. Create a new file on your desktop called
```
dfbt.sh
```
in TextEdit with the contents below:
```
#!/bin/sh

# Ask the user for the type of file
echo "Please enter the file extension:"
read TYPE

# Ask the user for the directory path
echo "Please enter the directory path:"
read DIR

# Use find command to search and delete files of the specified type
find "$DIR" -type f -name "*.$TYPE" -exec rm -f {} \;

echo "All .$TYPE files in $DIR have been deleted."
```
2. Save the file and run the commands below in the terminal, one by one:
```
shc -f ~/Desktop/dfbt.sh
```
```
sudo mv ~/Desktop/dfbt.sh.x /usr/local/bin/dfbt
```
Note: The second command may prompt for your password, enter it if asked.

Usage:
To use this thing, just run it like any other command in the terminal.
```
dfbt
```
It will first ask for the file type, answer with the file extension. However, do not put a dot before it (.m4a, etc), as the command will directly interpret it with a dot. Just answer with the plain file extension (m4a, key, etc). It will then ask for the directory that has the files, you cannot use the tilde user shortcut (~/). You have to enter the full path to the folder (/Users/your_user/path_to_folder) that contains the files.
