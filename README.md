# linux-fourth-mini-project


# Linux Permissions and User Management  Project Tasks

## What I Learned

Through this module, I gained a solid understanding of:

- **Linux file and directory permissions** (read, write, execute).
- How permissions are represented in both symbolic (e.g., `rwx`) and numeric (e.g., `755`) formats.
- How to change file permissions using `chmod`.
- Managing **users** and **groups** on a Linux system.
- Granting administrative privileges via the `sudo` group.
- Proper use of commands like `chown`, `chgrp`, `useradd`, `groupadd`, `usermod`, and `passwd`.
- Navigating the Linux filesystem and interpreting file metadata using `ls -l`.

---

##  How I Practiced

To master these concepts, I practiced by:

- Running various `chmod` commands on files and directories to understand how permission changes work.
- Creating and switching between multiple users using `useradd` and `su`.
- Creating and deleting groups with `groupadd` and `groupdel`.
- Changing file ownership using `chown` and modifying group ownership with `chgrp`.
- Testing user permissions by switching users and trying to access or modify files.
- Assigning administrative privileges to users and confirming with `sudo` commands.

---

## Task 1 Understanding File Permissions

###  Objective:
Learn how to read and manipulate Linux file permissions.

###  What I Did:

1. Created a file:
   ```
   touch script.sh
   ```

2. Viewed its permissions:
   ```
   ls -latr script.sh
   ```
![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/2.png?raw=true)

![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/3.png?raw=true)

3. Modified permissions:
   ```
   chmod +x script.sh

    added execution for all users
    ```
    chmod 755 script.sh
    ```
    
4. Interpreted the result:
   - `7` (Owner): `rwx` (read, write, execute)
   - `5` (Group): `r-x` (read, execute)
   - `5` (Others): `r-x` (read, execute)
   
   
5. Creating a user
  - to create a new user i used 'adduser'
  ```
  sudo adduser ebhosworks
  ```
  - created a password and confirm the password
  - enter the full name of the user
  - entered contact no of the user
  - in place of other i put the initial of the sex
  - and enter Y to confirm the detail and account creation
  ![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/5.png?raw=true)
---
# TASKS FOR ME AND HOW I DID THEM

##  Task 1: Switching and Modifying User Accounts

###  Switching User Accounts
To switch from my current user to another user (e.g., `ebhosworks`), I used the `su` (substitute user) command:
```
su ebhosworks
```
I was then prompted to enter the password for the `ebhosworks` account, and upon authentication, I switched to the user's environment.

###  Modifying User Password
To change the password of a user (e.g., `ebhosworks`), I used the `passwd` command:
```
sudo passwd ebhosworks
```
The system prompted me to enter the current password, enter the new password and confirm the new password. After updating the password, I tested it by logging in as `ebhosworks` with the new credentials to ensure it worked.
![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/re-new-password.png?raw=true)
---

##  Task 2: Managing Groups

### Creating a Group
I created a new group called `developers` using the `groupadd` command:
```
sudo groupadd developers
```

###  Adding Users to the Group
Next, I added the user `ebhosworks` to the `developers` group using:
```
sudo usermod -aG developers ebhosworks
```
The `-aG` flag ensures the user is added to the new group without removing them from existing groups.

###  Verifying Group Membership
To confirm that the user was added to the group, I used the `id` command:
```
id ebhosworks
```
The output listed `developers` among the user's groups, confirming successful addition.
![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/group-created.png?raw=true)

### Deleting a User
To delete any user, I used the following command:
```
sudo userdel username
```

---

##  Task 3: Side Hustle Group and Directory Setup

### Group Creation
I created a group named `devops`:
```
sudo groupadd devops
```

###  User Creation and Group Assignment
I created 5 users: `mary`, `mohammed`, `ravi`, `tunji`, and `sofia`, and added each of them to the `devops` group:
```bash
sudo adduser mary
sudo adduser  mohammed
sudo adduser  ravi
sudo adduser  tunji
sudo adduser  sofia
```

  - created a password and confirm the password
  - enter the full name of the user
  - entered contact no of the user
  - in place of other i put the initial of the sex
  - and enter Y to confirm the detail and account creation
![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/mary.png?raw=true)

![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/mohammed.png?raw=true)

![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/ravi.png?raw=true)

![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/tunji.png?raw=true)

![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/sofia.png?raw=true)

###  Adding Users to the Group
Next, I added the created user to the `devopss` 
```
sudo usermod -aG developers mary
sudo usermod -aG developers mohammed
sudo usermod -aG developers ravi
sudo usermod -aG developers tunji
sudo usermod -aG developers socia
```
![](https://github.com/adaezeokoduwa/linux-fourth-mini-project/blob/main/pics/add-user-devops.png?raw=true)

Then, I granted read and write permissions to the group:
```
sudo chmod g+rw /home/mary
sudo chmod g+rw /home/mohammed
sudo chmod g+rw /home/ravi
sudo chmod g+rw /home/tunji
sudo chmod g+rw /home/sofia
```

---

## Summary

- Switched and modified user accounts using `su` and `passwd`.
- Managed groups with `groupadd`, `usermod`, and `id`.
- Completed the side hustle task by creating users, adding them to a group, and managing their directory permissions.

This hands-on exercise helped me gain a solid understanding of Linux user/group administration and file permission management.
