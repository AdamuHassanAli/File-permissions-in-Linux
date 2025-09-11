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
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/f357ba8e700722b242799b361cd9ec9a95c0ab8b/Images/C%20images%201.png"/><br>
The <b>chmod</b> command changes the permissions on files and directories. <br>The first argument indicates what <b>permissions</b> should be changed,
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/f357ba8e700722b242799b361cd9ec9a95c0ab8b/Images/c-1.png"/><br>
And the second argument specifies the <b>file or directory</br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/f357ba8e700722b242799b361cd9ec9a95c0ab8b/Images/c-2.png"/>
<br/>

<p align="center">
<b>Screenshot 3:</b> <br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/c79e64269c42b7275119e8cfc827a6a4e6f86928/Images/003.png"/>
<br/>


<p align="center">
<b>Screenshot 4:</b> <br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/c79e64269c42b7275119e8cfc827a6a4e6f86928/Images/004.png"/>
<br/>



# 📌 Portfolio Project Summary  
As part of my role in supporting the research team at my organization, I was tasked with updating file and directory permissions within the `projects` directory. The current permissions did not properly reflect the required levels of authorization, which posed a security risk. To address this, I performed a detailed permissions audit and updated the access control settings using Linux commands.  

## How I Did the Project  
1. **Checked file and directory details**  
   - Used `ls -la` to list all files, including hidden ones, and review their current permissions.  
   - Interpreted the 10-character permission strings to understand who had read, write, and execute access.  

2. **Analyzed permission strings**  
   - Broke down each string into file type, user permissions, group permissions, and other permissions.  
   - Example: `-rw-rw-r--` → regular file, user/group have read+write, others have read-only.  

3. **Updated permissions on files**  
   - Removed **write access** for "other" users on files like `project_k.txt` using:  
     ```bash
     chmod o-w project_k.txt
     ```  
   - Modified permissions on hidden files such as `.project_x.txt` to allow only read access for user and group:  
     ```bash
     chmod u-w .project_x.txt  
     chmod g-w .project_x.txt  
     chmod g+r .project_x.txt  
     ```  

4. **Updated directory permissions**  
   - Adjusted the `drafts` directory so that only `researcher2` retained execute permissions:  
     ```bash
     chmod g-x drafts
     ```  
   - Verified changes with `ls -la` to confirm updates.  

## Result  
Successfully aligned file and directory permissions with organizational security policies. The updated permissions now prevent unauthorized write or execute access, reducing the risk of accidental modifications or misuse of sensitive project files.  

---

# 📌 Resume Project Section  

**Linux File Permissions Management**  
- Conducted a permissions audit and updated security controls for files and directories in a Linux environment.  
- Applied `ls -la` and `chmod` commands to review and modify access rights for users, groups, and others.  
- Restricted unauthorized write access to sensitive files and enforced user-specific directory execution permissions.  
- Improved system security posture by ensuring file permissions matched organizational authorization policies.  
