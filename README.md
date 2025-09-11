# Project Description  
The research team at my organization needed to update the file permissions for certain files and directories within the `projects` directory. The permissions did not properly reflect the level of authorization that should be given. Checking and updating these permissions helped keep the system secure.  

To complete this task, I performed the following steps:  

---

## 🔎 Check File and Directory Details  
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.
The following command lists all contents of the `projects` directory, including hidden files, and displays their permissions:  

<p align="center">
<b>Screenshot 1 :</b> <br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/ef72945c271fc8099fe154f6e6213cb138dfa0d7/Images/001.png"/>
<br/>
The first line of the screenshot displays the command I entered, and the other lines display the output. The code lists all contents of the projects directory. I used the ls command with the -la option to display a detailed listing of the file contents that also returned hidden files. The output of my command indicates that there is one directory named drafts, one hidden file named `.project_x.txt,` and five other project files. The 10-character string in the first column represents the permissions set on each file or directory.

<p align="center">
<b>Screenshot 2:</b> <br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/721869215fc16de5fdeffdd993d726625854f223/Images/002.png"/>
<br/>

<p align="center">
<b>Screenshot 3:</b> <br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/ef72945c271fc8099fe154f6e6213cb138dfa0d7/Images/001.pnga"/>
<br/>


<p align="center">
<b>Screenshot 4:</b> <br>
<img src="https://github.com/AdamuHassanAli/File-permissions-in-Linux/blob/ef72945c271fc8099fe154f6e6213cb138dfa0d7/Images/001.pnga"/>
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
