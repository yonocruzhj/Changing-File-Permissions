# File permissions in Linux

## Project description

The research team at this organization had to modify the file permissions for specific files and directories within the ***projects*** directory because the current permissions did not align with the appropriate authorization levels. Reviewing and updating these permissions enhanced the overall security of their system via the principle of least privilege. To accomplish this, I used Linux commands to edit authorization.

## Goals

The goal of this project was to successfully modify access to files and directories within the ***projects*** directory to enhance security posture of the organization.

<h2>Environments Used </h2>

- <b>Linux</b> 

## File and directory details

The following code below shows the Linux commands used to see the existing permissions set in the ***projects*** directory. The first line showed the command I entered, and the following  lines displayed the output. The code lists all contents of the ***projects*** directory. I used the **ls** command with the **\-la** option to reveal the file contents that also returned hidden files. The output of my command displayed that there is one directory named **drafts**, one hidden file named **.project\_x.txt**, and five other project files. Lastly, the 10-character string in the first column represents the permissions set on each file or directory. 
<p align="center">
<img src="https://imgur.com/yQLYf4d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

## Describe the permissions string

The permissions string that will be used is the last file for **project t.txt**. The permissions string is in 10 characters “-rw-rw-r–.” The first character in a string dictates if it is a directory or not, since it has a hyphen instead of the letter **d** then we know this is a file. The next 3 characters (2-4) in the string describe the permissions for the user. The only letters here are r and w which mean the user has read and write permissions but not execute permissions within the file. The next 3 characters (5-7) represent the group permissions to the file which also happen to be r and w, so they have the read and write permissions. The last 3 characters (7-10) in the string represent the others that have access to the file. The only character here is r which means the others have read permissions only to the file. R or the read permission grants permission, so the content can be read. W or the write permission grants permission for the file to be modified. X is the one that is not labeled here, but X is the execute permission which allows the file to be executed if possible.

## Change file permissions

The organization decided that no files should have write access for the "other" user group. To ensure compliance, I reviewed the file permissions I previously documented and identified that \`**project\_k.txt**\` required the removal of write access for "other." The following code demonstrates I successfully removed the write access for the “other” group for **project\_k.txt**.   
<p align="center">
<img src="https://imgur.com/nNRFKhr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />


## Change file permissions on a hidden file

The research team does not want anyone to have write access to **project\_x.txt**. They want the user and group to only have read access. The code below shows I successfully removed write access from all groups and only left the read access for the user and group. The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The hidden file is ‘**.project\_x.txt’** because it starts with a period (**.**). I used the **chmod** **u=r** and **g=r** to only add read access to the user and group.

<p align="center">
<img src="https://imgur.com/sVmRk3o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

## Change directory permissions

The organization wanted the **researcher2** user to have access to the **drafts** directory and its contents. This means that no one other than **researcher2** should have execute permissions.  
The following code below showed how I used Linux commands to change the permissions:
<p align="center">
<img src="https://imgur.com/QGCVxOL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />


The output displayed the permission listing for the files and directories. Line 1 indicates the current directory (**projects**), and line 2 indicates the parent directory (**home**). Line 3 indicates a regular file titled **.project\_x.txt**. Line 4 is the directory (**drafts**) with restricted permissions. Initially, the group had execute permissions, so I used the **chmod** **g-x** command to remove them. Now only **researcher2** has execute permissions. The **researcher2** user already had execute permissions, so they did not need to be added.

## Summary

My job was to assign and modify permissions for certain directories and files of the authorized users. Through the Linux command line, I changed file, hidden file, and directory permissions for the user, group users, and other users based on what the company requested. I used the **ls \-la** to check permissions for the projects directory as well as the **chmod** to modify permissions for files and directories. These commands helped me enhance security posture as well as simulate the principle of least privilege. 


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
