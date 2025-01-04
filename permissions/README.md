# Linux Permissions

## Viewing permissions
To view Linux permissions, you can use the ```ls -l <file>``` for a file or ```ls -ld <dir>``` for a directory.

Here's an example of a file permission: ```-rwxr--r-- 1 root 197609 0 Jan  4 16:44```. Here's an example of a file permission: ```drwxr--r-- 1 root 197609 0 Jan  4 16:44```.

The first char tells you if it's a file (-) or directory (d). The next nine characters tell you the read, write, and execute privileges for a user, group, and others. In the above example, both the file and directory permissions give the `root` user `read`, `write`, and `execute` access.

## Modifying permissions

Permissions on Linux files and directories can be modified using the `chmod` command. There are two notations that can be used:
1. Numerical notation
2. Symbolic notation

### Numerical notation

Here, you must set permission for the user, group, and others at the same time using a single number for each one. Each number represents the levels of access (r, w, and x) for the user, group and others. Each level of access has a number mapped to it: r = 4; w = 2; and x = 1.

To set read, write, and execut access: 4 + 2 + 1 = 7
To set read and write access: 4 + 2 = 6
To set read and execute access: 4 + 1 = 5
To set only read access: 4

#### Examples:
Set read and write access to user and group and no access to others: 
`chmod 660 file.txt`

### Symbolic notation

Here, you can use a more readable notation to set permissions. To set permissions for the user, use `u=`. For group, use `g=` and for others use `o=`

#### Examples
Set read and write access to user and group and no access to others: 
`chmod u=rw,g=rw,o= file.txt` 

You can also add/remove permissions for user, group or others using `+`/`-`:
* `chmod u+x file.txt` (adds execute permission to the user)
* `chmod o-x file.txt` (removes execute permission from others)
* `chmod ug-x file.txt` (removes execute permission from user and group)
* `chmod a-w file.txt` (removes write permission from user, group, and others)