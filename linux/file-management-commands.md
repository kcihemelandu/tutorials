# File Management Commands

Linux uses some conventions for present and parent directories. This can be a
little confusing for beginners.

Whenever you are in a terminal in Linux, you will be in what is called the
current working directory. Often your command prompt will display either the
full working directory, or just the last part of that directory. Your prompt
could look like one of the following:

```sh
user@host ~/somedir $
user@host somedir $
user@host /home/user/somedir $
```

> which all that your current working directory is `/home/user/somedir`.

In Linux .. represents the parent directory and . represents the current
directory.

Therefore, if the current directory is `/home/user/somedir`, then
`cd ../somedir will` not change the working directory.

Below lists some of the most used file management commands

## Directory Navigation

| Command             | Utility                |
| ------------------- | ---------------------- |
| `pwd`               | Get the full path of the current working directory  |
| `cd -`              | Navigate to the last directory you were working in. |
| `cd ~` or just `cd` | Navigate to the current user's home directory. |
| `cd ..`             | Go to the parent directory of current directory (mind the space between cd and ..) |

## Listing files inside a directory

| Command           | Utility |
| ----------------- | ------- |
| `ls -l`           | List the files and directories in the current directory in long (table) format (It is recommended to use -l with ls for better readability). |
| `ls -ld dir-name` | List information about the directory dir-name instead of its contents. |
| `ls -a`  | List all the files including the hidden ones (File names starting with a . are hidden files in Linux). |
| `ls -F`  | Appends a symbol at the end of a file name to indicate its type (* means executable, / means directory, @ means symbolic link, = means socket, | means named pipe, > means door). |
| `ls -lt` | List the files sorted by last modified time with most recently modified files showing at the top (remember -l option provides the long format which has better readability). |
| `ls -lh` | List the file sizes in human readable format. |
| `ls -lR` | Shows all subdirectories recursively. |
| `tree`   | Will generate a tree representation of the file system starting from the current directory. |

## File/directory create, copy and remove

| Command | Utility |
| ------- | ------- |
| `cp -p source destination` | Will copy the file from source to destination. -p stands for preservation. It preserves the original attributes of file while copying like file owner, timestamp, group, permissions etc. |
| `cp -R source_dir destination_dir` | Will copy source directory to specified destination recursively. |
| `mv file1 file2` | In Linux there is no rename command as such. Hence mv moves/renames the file1 to file2. |
| `rm -i filename` | Asks you before every file removal for confirmation. **IF YOU ARE A NEW USER TO LINUX COMMAND LINE, YOU SHOULD ALWAYS USE** rm -i. You can specify multiple files. |
| `rm -R dir-name` | Will remove the directory dir-name recursively. |
| `rm -rf dir-name` | Delete a non-empty directory (i.e. contains files and/or other directories): Will remove the directory dir recursively, ignoring non-existent files and will never prompt for anything. **BE CAREFUL USING THIS COMMAND!** You can specify multiple directories. |
| `rmdir dir-name` | Will remove the directory dir-name, if it's empty. This command can only remove empty directories. |
| `mkdir dir-name` | Create a directory dir-name. |
| `mkdir -p dir-name/dir-name` | Create a directory hierarchy. Create parent directories as needed, if they don't exist. You can specify multiple directories. |
| `touch filename` | Create a file filename, if it doesn't exist, otherwise change the timestamp of the file to current time. |

## Working with files

| Command | Utility |
| ------- | ------- |
| `cat filename` | View the contents of a file: |
| `less filename` | View the content of a file with pager (one screenful at a time): |
| `head filename` | View the first several lines of a file: |
| `tail filename` | View the last several lines of a file: |
| `vi filename` | Edit a file: |
| `mv filename dirname` | Move a file into a directory (folder) |
| `rm filename` | Removes (or Deletes) the file |

## File/directory permissions and groups

| Command | Utility |
| ------- | ------- |
| `chmod <specification> filename` | Change the file permissions. Specifications => `u` user, `g` group, `o` other, `+` add permission, `-` remove, `r` read, `w` write, `x` execute. |
| `chmod -R <specification> dirname` | Change the permissions of a directory recursively. If you want change permission of a directory and everything within that directory, use this command. |
| `chmod go=+r myfile` | Add read permission for the owner and the group. |
| `chmod a +rwx myfile` | Allow all users to read, write or execute myfile. |
| `chmod go -r myfile` | Remove read permission from the group and others. |
| `chown owner1 filename` | Change ownership of a file to user owner1. |
| `chgrp grp_owner filename` | Change primary group ownership of file filename to group grp_owner. |
| `chgrp -R grp_owner dir-name` | Change primary group ownership of directory dir-name to group grp_owner recursively. To change group ownership of a directory and everything within that directory, use this command. |