# Project Description  
The research team at my organization needed to update the file permissions for certain files and directories within the `projects` directory. The permissions did not properly reflect the level of authorization that should be given. Checking and updating these permissions helped keep the system secure.  

To complete this task, I performed the following steps:  

---

## 🔎 Check File and Directory Details  
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.
The following command lists all contents of the `projects` directory, including hidden files, and displays their permissions:  

<p align="center">
<b>Screenshot 1 :</b> <br>
The first line of the screenshot displays the command I entered, and the other lines display the output.<br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/7505ab5d7d5f895b3031d0ffe8c66e8c0562b66a/Images/d-1.png"/><br>
The code lists all contents of the projects directory. <br> I used the <b>ls</b> command with the <b>-la</b> option to display a detailed listing of the file contents that also returned hidden files.<br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/ef72945c271fc8099fe154f6e6213cb138dfa0d7/Images/001.png"/><br>
The output of my command indicates that there is one directory named <b>drafts,</b> <br>one hidden file named <b>.project_x.txt,</b> and five other project files.<br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/1d6e853fd759a56ed23231902b371f12928d0b62/Images/d-2.png"/><br>
The 10-character string in the first column represents the permissions set on each file or directory.<br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/12e3d001df1289883e86871ab027b2a50527aca1/Images/d-3.png"/>
<br/>
   
## Describe the permissions string

The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:<br>
<p align="center">
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/12e3d001df1289883e86871ab027b2a50527aca1/Images/d-3.png"/><br>
   
- **1st character**: This character is either a `d` or hyphen (`-`) and indicates the file type.
  - `d`: Directory
  - `-`: Regular file

- **2nd-4th characters**: These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the **user**. A hyphen (`-`) indicates that permission is not granted.

- **5th-7th characters**: These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for the **group**. A hyphen (`-`) indicates that permission is not granted.

- **8th-10th characters**: These characters indicate the read (`r`), write (`w`), and execute (`x`) permissions for **others** (all other users on the system). A hyphen (`-`) indicates that permission is not granted.

## Example

The file permissions for `project_t.txt` are `-rw-rw-r--`.

- **First character** (`-`): Regular file (not a directory)
- **User permissions** (`rw-`): Read and write permissions, no execute
- **Group permissions** (`rw-`): Read and write permissions, no execute  
- **Other permissions** (`r--`): Read permission only, no write or execute
</p>

## ✏️ Change File Permissions
The organization decided that others should not have write access to any files. To remove write access for others on project_k.txt.<br>
The following code demonstrates how I used Linux commands to do this:

<p align="center">
<b>Screenshot 2:</b> <br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/721869215fc16de5fdeffdd993d726625854f223/Images/002.png"/><br>
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/f357ba8e700722b242799b361cd9ec9a95c0ab8b/Images/c-1.png"/><br>
The <b>`chmod`</b> command changes the permissions on files and directories.<br>The first argument indicates what <b>permissions</b> should be changed
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/f357ba8e700722b242799b361cd9ec9a95c0ab8b/Images/c-1.png"/><br>
And the second argument specifies the <b>file or directory
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/f357ba8e700722b242799b361cd9ec9a95c0ab8b/Images/c-2.png"/><br>
In the above example, I removed write permissions from others for the `project_k.txt` file. After this, I used `ls -la` to review the updates I made.
</b>

## 🔒 Change File Permissions on a Hidden File
The research team at my organization recently archived `project_x.txt.` They do not want anyone to have write access to this project, but the user and group should have read access. 
The following code demonstrates how I used Linux commands to change the permissions:

<p align="center">
<b>Screenshot 3:</b> <br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/c79e64269c42b7275119e8cfc827a6a4e6f86928/Images/003.png"/>
<br/>The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know `.project_x.txt` is a hidden file because it starts with a period (.). In this example, I removed write permissions from the user and group, and added read permissions to the group. I removed write permissions from the user with `u-w.` Then, I removed write permissions from the group with `g-w,` and added read permissions to the group with `g+r`. 

## 📂 Change Directory Permissions
My organization only wants the `researcher2` user to have access to the drafts directory and its contents. This means that no one other than `researcher2` should have execute permissions.
The following code demonstrates how I used Linux commands to change the permissions:

<p align="center">
<b>Screenshot 4:</b> <br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/c79e64269c42b7275119e8cfc827a6a4e6f86928/Images/004.png"/>
<br/>The output here displays the permission listing for several files and directories. Line 1 indicates the current directory (projects), and line 2 indicates the parent directory (home). Line 3 indicates a regular file titled `.project_x.txt.` Line 4 is the directory (drafts) with restricted permissions. Here you can see that only `researcher2` has execute permissions.  It was previously determined that the group had execute permissions, so I used the `chmod` command to remove them. The `researcher2` user already had execute permissions, so they did not need to be added.

## ✅ Summary
I changed multiple permissions to match the level of authorization my organization wanted for files and directories in the projects directory. The first step in this was using `ls -la` to check the permissions for the directory. This informed my decisions in the following steps. I then used the `chmod` command multiple times to change the permissions on files and directories.


