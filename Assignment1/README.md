# Assignment 4: Creating a User with Limited Privileges

## Objective
To implement the *Principle of Least Privilege* by setting up a user account without administrative (sudo) permissions.

---

## Step 1: Add a New User Account (student01)

Run the following command:
bash
sudo adduser student01


The system will prompt you for details such as full name and contact information (optional). Press *Enter* to skip or fill them in.

To confirm successful creation, type:
bash
groups student01

This will display the groups the user belongs to (see Fig.2).

Fig.1: Creation of User and Entering Data about User ‘student01’  
Fig.2: Verification of Creation of User

---

## Step 2: Remove Administrative Rights from student01

Execute:
bash
sudo usermod -G student01 student01


This removes student01 from the sudo group, preventing execution of sudo commands.

Check the groups again using:
bash
groups student01

You should no longer see the sudo group listed (see Fig.3).

*Fig.3: Removing sudo privileges from student01*

---

## Step 3: Confirm that student01 No Longer Has sudo Access

You can verify this in two different ways:

### Method 1: Switch to the student01 account directly
bash
su - student01

Then attempt any sudo command — access should be denied (see Fig.4).

*Fig.4: Confirmation that sudo privileges are denied, through terminal in main user*

---

### Method 2: Log out and log in as student01
Log out from the current user (e.g., kali) and log in as student01 (see Fig.5).  
Once logged in, open the terminal and run any sudo command. It should be denied (see Fig.6).

*Fig.5: Logging in to student01*  
*Fig.6: Confirmation that sudo privileges are denied, through terminal in student01*

---

## Why Limiting User Privileges is Important

- Ensures adherence to the *Principle of Least Privilege*  
- Minimizes potential harm if an account is compromised  
- Blocks any unauthorized changes to the system  
- Reduces system attack surface and enhances overall security  

---

## Conclusion
The user account student01 was created and stripped of administrative privileges.  
This exercise highlights how proper user privilege management strengthens Linux system security.
