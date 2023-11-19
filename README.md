<h1>

    Securing Systems Exploring File Permissions in Linux

</h1>

<h2>General Description</h2>
Explore my Linux security expertise. Meticulous file permission management at enhancing system security. Check commits for insights into fortifying Linux environments. I detailed meticulous checks, permission deconstruction, and strategic use of Linux.
Witness how I fortified sensitive data, managed hidden files, and implemented access restrictions to align with organizational security policies.
<br />


<h2> Utilities Used</h2>

- <b>Standard Linux commands for file management, including ls and chmod.</b> 

<h2>Environments Used </h2>

- <b>Linux</b> 

<h2>Command walk-through:</h2>

<h2>Project Description</h2>
The research team at my organization needed to update the file permissions for certain files and directories within the projects directory. The permissions previously did not reflect the level of authorization that should be given. Checking and updating these permissions helped make the system secure. To complete this task, I performed the following tasks:

<br />

<h3>Check file and directory details</h3>
 
<p align="center">
The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system: <br/>
<br />
<br />
<img src="https://github.com/Pentyfada/Pentyfada/assets/139077088/9b59e22b-aee4-402b-83a4-43f7b116eae2" height="80%" width="80%" alt="Check File Directory Steps"/>
<br />

The first line of the screenshot displays the command I entered, and the other lines display the output. The code lists all contents of the projects directory. I used the ls command with the -la option to display a detailed listing of the file contents that also returned hidden files. The output of my command indicates that there is one directory named drafts, one hidden file named .project_x.txt, and five other project files. The 10-character string in the first column represents the permissions set on each file or directory.

<h4>Description of the permissions string</h4>
The 10-character string can be deconstructed to determine who is authorized to access the file and their specific permissions. The characters and what they represent are as follows:

●	1st character: This character is either a d or hyphen (-) and indicates the file type. If it’s a d, it’s a directory. If it’s a hyphen (-), it’s a regular file.

●	2nd-4th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the user. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.

●	5th-7th characters: These characters indicate the read (r), write (w), and execute (x) permissions for the group. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.

●	8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for other. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.

For example, the file permissions for project_t.txt are -rw-rw-r--. Since the first character is a hyphen (-), this indicates that project_t.txt is a file and not a directory. The second, fifth, and eighth characters are all r, which indicates that user, group, and other all have read permissions. The third and sixth characters are w, which indicates that only the user and group have write permissions. No one has execute permissions for project_t.txt.

<h3>Change file permissions</h3>
The organization determined that other shouldn't have write access to any of their files. To comply with this, I referred to the file permissions that I previously returned. I determined project_k.txt must have the write access removed for other.




  
<br />
<br />
The following code demonstrates how I used Linux commands to do this in the screenshot:  <br/>
<img src="https://github.com/Pentyfada/Pentyfada/assets/139077088/53077cc0-d18b-4d02-bc21-8bc7192698b7" height="80%" width="80%" alt="Check File Directory Steps"/>
<br />
<br />

The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. The chmod command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this task, I removed write permissions from other for the project_k.txt file. After this, I used ls -la to review the updates I made.

<br />

<h3>Change file permissions on a hidden file
</h3>
The research team at my organization recently archived project_x.txt. They do not want anyone to have write access to this project, but the user and group should have read access. 
<br />
<br />

The following code demonstrates how I used Linux commands to change the permissions: <br/>
<img src="https://github.com/Pentyfada/Pentyfada/assets/139077088/b6f1ff3c-8a84-4f6d-9098-de7fbd6f81f1" height="80%" width="80%" alt="Check File Directory Steps"/>
<br />
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know .project_x.txt is a hidden file because it starts with a period (.). In this task, I removed write permissions from the user and group, and added read permissions to the group. I removed write permissions from the user with u-w. Then, I removed write permissions from the group with g-w, and added read permissions to the group with g+r. 

<h3>Change directory permissions
</h3>
My organization only wants the researcher2 user to have access to the drafts directory and its contents. This means that no one other than researcher2 should have execute permissions.



The following code demonstrates how I used Linux commands to change the permissions:  <br/>
<img src="https://github.com/Pentyfada/Pentyfada/assets/139077088/fa2ae4a7-f381-4104-9d98-755aa145d613" height="80%" width="80%" alt="Check File Directory Steps"/>
<br />
<br />
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I previously determined that the group had execute permissions, so I used the chmod command to remove them. The researcher2 user already had execute permissions, so they did not need to be added.
<h2>Summary</h2>
I changed multiple permissions to match the level of authorization my organization wanted for files and directories in the projects directory. The first step in this was using ls -la to check the permissions for the directory. This informed my decisions in the following steps. I then used the chmod command multiple times to change the permissions on files and directories.

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
