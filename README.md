# Project: Enforcing Security Best Practices with Linux Permissions. 

  As part of the Day0 Academy Course, I worked on a project focused on the “Least Privilege” principle. On a Linux system, I managed file permissions to ensure users had only the access they truly needed. This hands-on experience taught me how careful permission management strengthens security while keeping systems functional and efficient.
  
## Project Overview

 - Scenario

  While working as an IT professional in a major finance organization, I led a project to enforce the “Least Privilege” principle on a Linux system. The focus was on the /home/researcher2/projects directory, a key area used by the researcher2 account and the research_team group, where careful permission management was critical for security.

 - Key Actions

Permission Audit: Conducted a thorough review of all files, including hidden ones, to identify permissions that didn’t meet security standards.

Permission Adjustment: Applied precise changes to user, group, and other permissions using Linux command-line tools, ensuring everyone had only the access they truly needed while maintaining productivity.

This project strengthened my hands-on Linux skills and reinforced the importance of balancing security with usability in real-world environments.

 - Objective
   
The goal of this project was to strengthen data security by applying the “Least Privilege” principle—reducing potential vulnerabilities while keeping systems fully functional.

 - Steps
 
Step 1 – Reviewing File and Directory Details

I began by examining the files and directories inside the projects folder. Using the ls -la command, I was able to display all permissions, including those for hidden files, to get a complete picture of the current access settings.

<img width="1108" height="222" alt="Screenshot 2025-08-19 at 10 46 19 PM" src="https://github.com/user-attachments/assets/3eb115fb-73d0-414a-9095-21ff055304ec" />

Step 2 – Interpreting the Permissions String

After running the ls -la command, I reviewed the permissions assigned to each file and directory, including hidden ones. Focusing on the drafts directory, I noted that the user had read, write, and execute permissions, the group had only execute permissions, and others had no access at all. The permission string for this setup was: drwx--x---.

<img width="1108" height="483" alt="Screenshot 2025-08-19 at 11 27 27 PM" src="https://github.com/user-attachments/assets/c12848a6-2b98-415b-97d1-8f4decffdebe" />

Step 3 – Changing File Permissions

According to the organization’s policy, no files should allow write access for “others.” During my review, I found that master00.txt was the only file violating this rule. To correct it, I used the command chmod 664 master00.txt or chmod o-w master00.txt to remove the unnecessary permission. I then verified the change with ls -la to ensure compliance.

<img width="1152" height="663" alt="Screenshot 2025-08-20 at 12 06 33 AM" src="https://github.com/user-attachments/assets/e6f930ac-be01-4ca7-b21f-8218dafc176a" />


