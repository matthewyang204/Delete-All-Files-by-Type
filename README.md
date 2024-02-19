# Delete All m4a
Ever converted all your m4a files to mp3 on your Mac, only to find it hard to delete all of the m4a after you're done? This is a solution!

Installation:
1. Create a new file on your desktop called
```
deleteallm4a.sh
```
in TextEdit with the contents below:
```
#!/bin/sh

# Ask the user for the directory path
echo "Please enter the directory path:"
read DIR

# Use find command to search and delete .m4a files
find "$DIR" -type f -name "*.m4a" -exec rm -f {} \;

echo "All .m4a files in $DIR have been deleted."
```
2. Save the file and run the commands below in the terminal, one by one:
```
shc -f ~/Desktop/deleteallm4a.sh
```
```
sudo mv ~/Desktop/deleteallm4a.sh.x /usr/local/bin/deleteallm4a
```
Note: The second command may prompt for your password, enter it if asked.

Usage:
To use this thing, just run it like any other command in the terminal.
```
deleteallm4a
```
It will ask for the directory that has .m4a files, you cannot use the tilde user shortcut (~/). You have to enter the full path to the folder (/Users/your_user/path_to_folder) that contains .m4a files.
