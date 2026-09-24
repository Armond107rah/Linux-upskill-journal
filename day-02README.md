# Day 02 - Basic Navigation

## Objective

We will be focused on basic Linux filessystem navigation, working with absolute and relative paths, creating directory structures and safely cleaning up created resources. 

##Environment
- Ubuntu 24.04 LTS
- DigitalOCean Droplet
- Bash shell
_User: root

--

## 1.Find the Starting Location
## Command
```bash
'pwd'
```
## Result
``bash
'/root'
```
## What I learned
The pwd command means Print Working Directory. it shows the complete absolute path of the directory I am currently working in.
This is important because Linux commands often depend on the directory I am currently inside.

## 2. Navigate Using an Absolute Path
The system log directory is:
```bash
'/var/log'
```
## Comands
```bash
'cd /var/log'
```
```bash
'pwd'
```
Result gives you /var/log

## What I learned
An absolute path starts from the root directory /. Absolute paths are useful because they identify an exact location regardless of my current directory.

## 3. Navigate Using a Relative Path
Starting from: /var/log
I moved one level upward and then back into the log directory using only a relative path.
## Command
```bash
cd ../log
```
Then I verified the location: pwd which results me into getting /var/log

## What I learned
In Linux: 
. = current directory
.. = parent directory
Therefore: cd ../log means 1. Move from /var/log  up to /var 2. Enter the log directory 3. End up back in /var/log

I also learned that relative paths depend on m current location. If I run cd ../log from the wrong directory, Linux may return: No such file or directory

## 4. Return to the Home Directory
Instead of typing the full path manually, I returned home with:
cd
I could also use:
```bash
cd ~
```
Then I verified the result: pwd Which gave me the result /root
## What I learned
The ~ symbol represents the current user's home directory. Because I was logged in as the root user: ~ = /root

## 5. Find Hidden Files and Directories
 displayed all entries in my home directory using:
```bash
ls

-la
```

The hidden entries shown were:
```bash
.bash_history
.bashrc
.cache
.cloud-locale-test.skip
.lesshst
.profile
.ssh
.wget-hsts
```
Hidden Entry Count: 8

## What I learned
Linux hidden files and directories normally begin with a period ..

Examples include:

.bashrc
.profile
.ssh

The ls -la command shows hidden files and also provides detailed information such as:

-Permissions
-Owner
-Group
-File size
-Modification time
-File or directory name

## 6. Identify Directories
I used a detailed listing:
```bash
ls -la
```
A directory starts wit hthe letter d in the permission field.
For example:
```bash
drwx-----
```
## What I learned
The first character in a long listing helps identify the object type.

Examples:

- d = directory
- - = regular file
- l = symbolic link
## Create a Directory Structure
