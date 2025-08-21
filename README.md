# Project: Enforcing Security Best Practices with Linux Permissions. 

  As part of the Day0 Academy Course, I worked on a project focused on the “Least Privilege” principle. On a Linux system, I managed file permissions to ensure users had only the access they truly needed. This hands-on experience taught me how careful permission management enhances security while maintaining systems' functionality and efficiency.c
  
## Project Overview

 - Scenario

  While working as an IT professional in a major finance organization, I led a project to enforce the “Least Privilege” principle on a Linux system. The focus was on the /home/blue-team/projects directory, a key area used by the researcher2 account and the research_team group, where careful permission management was critical for security.

 - Key Actions

Permission Audit: Conducted a thorough review of all files, including hidden ones, to identify permissions that didn’t meet security standards.

Permission Adjustment: Applied precise changes to user, group, and other permissions using Linux command-line tools, ensuring everyone had only the access they truly needed while maintaining productivity.

This project strengthened my hands-on Linux skills and reinforced the importance of balancing security with usability in real-world environments.

 - Objective
   
The goal of this project was to strengthen data security by applying the “Least Privilege” principle—reducing potential vulnerabilities while keeping systems fully functional.

 - Steps
 
Step 1 – Reviewing File and Directory Details

I began by examining the files and directories inside the projects folder. Using the ls -la command, I was able to display all permissions, including those for hidden files, to get a complete picture of the current access settings.


<img width="934" height="103" alt="image" src="https://github.com/user-attachments/assets/c3aa6d83-06fc-4efe-8a74-4a3ba87ffb01" />

Step 2 – Interpreting the Permissions String

After running the ls -la command, I reviewed the permissions assigned to each file and directory, including hidden ones. Focusing on the drafts directory, I noted that the user had read, write, and execute permissions, the group had only execute permissions, and others had no access at all. The permission string for this setup was: drwx--x---.

<img width="934" height="315" alt="image" src="https://github.com/user-attachments/assets/18e8cd1c-318a-4e4e-bbfd-4c65d5ba1574" />



Step 3 – Changing File Permissions

According to the organization’s policy, no files should allow write access for “others.” During my review, I found that master00.txt was the only file violating this rule. To correct it, I used the command chmod 664 master00.txt or chmod o-w master00.txt to remove the unnecessary permission. I then verified the change with ls -la to ensure compliance.

<img width="827" height="460" alt="image" src="https://github.com/user-attachments/assets/fad2c3ad-d640-4dbf-b51c-6987ccca2343" />



Additionally, the organization’s policy states that group members should not have read access to master000.txt. To enforce this, I removed the group’s read permission with the command chmod g-r master000.txt, then verified the update using ls -la to confirm the restriction was applied correctly.

<img width="829" height="648" alt="image" src="https://github.com/user-attachments/assets/b300320d-326d-44b4-a557-a84724da9dd0" />


Step 4 – Restricting Group Access
The organization’s policy states that group members should not have read access to project_m.txt. To enforce this, I removed the group’s read permission with the command chmod g-r project_m.txt, then verified the update using ls -la to confirm the restriction was applied correctly.


<img width="827" height="831" alt="image" src="https://github.com/user-attachments/assets/5d1f827a-9eb7-4dce-86b2-e2907e93975a" />


Step 5 – Updating Permissions on a Hidden File
While reviewing the directory with ls -la, I found a hidden file named .project_x.txt. Both the user and the group had write permissions, which violated policy. To fix this, I removed those permissions using chmod u-w,g-w .project_x.txt, ensuring the file complied with security requirements.

<img width="827" height="150" alt="image" src="https://github.com/user-attachments/assets/b3b02dc7-e089-4131-aeb6-b3ad2ec4e369" />



Step 6 – Securing Directory Access
In the final step, I focused on the drafts directory. To align with policy, I adjusted its permissions so that only the researcher2 user retained access, ensuring sensitive files were properly restricted.

<img width="828" height="277" alt="image" src="https://github.com/user-attachments/assets/d8d52c6d-2aeb-48b9-a751-33cfd2f682d2" />


Step 7 – Removing Group Execute Permissions
When reviewing the drafts directory with ls -l, I noticed that the group still had execute permissions. To meet policy requirements, I removed this access using chmod g-x drafts, then confirmed the change with ls -l to ensure compliance.


Project Summary

In this project, I took on the responsibility of enforcing the “Least Privilege” principle as an IT professional within a large finance organization. The focus was the /home/researcher2/projects directory, owned by the researcher2 user, a member of the research_team group, where careful permission management was critical.

The process began with a thorough review of all files and directories—including hidden ones—using the ls -la command to display detailed permissions. During the audit, several items were found to be out of compliance with the organization’s security policy:

project_k.txt: Others had write access, which was removed using chmod o-w project_k.txt.

project_m.txt: The group had read access against policy, removed with chmod g-r project_m.txt.

.project_x.txt (hidden file): Both the user and group had write permissions, removed with chmod u-w,g-w .project_x.txt.

drafts directory: Access was restricted so that only researcher2 could use it, and the group execute permission was removed with chmod g-x drafts.

Each change was verified with ls -la or ls -l to ensure compliance and correctness.

This project not only demonstrates my ability to apply key security principles in a Linux environment but also highlights my hands-on proficiency with command-line tools to effectively manage and secure file and directory permissions, balancing security and operational functionality.
