
### Linux Commands

#### User and Group Management
- `useradd` - Add a new user
- `userdel` - Delete a user
- `usermod` - Modify a user
  - `-G` - Add user to additional groups(part of multiple group)
  - `-g` - Change the default group
- `groupadd` - Add a new group
- `groupdel` - Delete a group

**Example:**
```bash
useradd simpu           # create user with group name simpu 
useradd -g QA simpu     # Create a user named 'simpu' and assign them to the 'QA' group
id <username>           # to view the user info including UID,GUID,group
usermod -G QA simpu     # uid=1001(simpu) gid=1001(simpu) groups=1001(simpu),1002(QA)
usermod -g QA simpu     # uid=1001(simpu) gid=1002(QA)    groups=1002(QA)
```


### File Permissions and Ownership

#### `chmod` (Change File Mode Bits)
- **Permissions Values:**
  - `4` - Read
  - `2` - Write
  - `1` - Execute
  - `0` - No-execute

- **Permission Combination:** Permissions are set in the order: **owner** -- **group** -- **others**

**Examples:**
- `chmod 755 file.txt` 
  - **Owner:** Read(`4`), Write(`2`), Execute(`1`) = (`7`)
  - **Group:** Read(`4`), Execute(`1`) = (`5`)
  - **Others:** Read(`4`), Execute (`1`) = (`5`)

#### `chown` (Change File Owner and Group)
- **Usage:**
  - `chown [owner][:group] filename`
  - **owner** - New owner of the file
  - **group** - New group of the file (optional)

**Examples:**
- `chown user:group file.txt` 
  — Changes both the owner to `user` and the group to `group`.

- `chown user file.txt`
  — Changes only the owner to `user`, keeping the current group.

- `chown :group file.txt`
  — Changes only the group to `group`, keeping the current owner.


### Linux Commands

| Command                         | Description                                                            |
|---------------------------------|------------------------------------------------------------------------|
| `find ~ -name 'error.sh'`       | Search for files named `error.sh` within the user's home directory and its subdirectories |
| `find . -name main.tf`          | Search for files and directories in the curent directory                                  |
| `du -h`                         | Lists the sizes of all files and directories recursively like (tree)   |
| `du -sh *`                      | Lists the sizes of each file and directory in the current directory    |
| `df -h`                         | Display information about disk space usage                            |
| `tar -xvc file.tar file.txt`    | To create archive file                                                 |
| `tar -xvf file.tar`             | To unarchive file                                                       |
| `tail -f /var/log/auth.log`     | View file from end of the line & monitor in realtime                   |
| `netstat`                       | Displays active TCP,UDP connections, ports on which the computer is listening, routing table, network protocol statics |
| `traceroute`                    | Trace the route packets how data travels on internet from your computer to destination.                        |
| `nslookup`                      | Find the IP address associated with a domain name                     |
| `systemctl`                     | Control and manage systemd services                                   |
| `journalctl`                    | Query and display messages from the journal                           |
| `wc -l names.txt`               | Count number of lines                                                  |
| `ping`                          | Check if a network connection to a host is alive                      |
| `uptime`                        | Show how long the system has been running                             |
| `ifconfig`                      | Configure network interfaces                                          |
| `wget`                          | Download files from the web                                           |
| `awk`                           | Used to handle structured data/output                                |
| `sed`                           | Stream editor used to manipulate text                                 |
| `whoami`                        | Show current logged in user                                           |
| `lscpu`                         | Display CPU architecture information                                  |
| `hostname`                      | Show or set the system's hostname                                     |
| `export`                        | Set environment variables                                             |
| `env`                           | Display all environment variables                                     |
| `curl`                          | Transfer data from or to a server                                    |
| `top`                           | Used to show the CPU usage, memory usage, load avg, process, Swap memory |

