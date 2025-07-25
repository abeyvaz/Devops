# Week 2: Linux System Administration & Automation
---

## 📌 Tasks

### **1️⃣ User & Group Management**
- Learn about Linux **users, groups, and permissions** (`/etc/passwd`, `/etc/group`).
- **Task:**  
  - Create a user `devops_user` and add them to a group `devops_team`.
    >> sudo addgroup devops_team
    >> sudo useradd -a devops_user devops_team  
  - Set a password and grant **sudo** access.
    >> sudo passwd devops_user || sudo useradd devops_user sudo   

---

### **2️⃣ File & Directory Permissions**
- **Task:**  
  - Create `/devops_workspace` and a file `project_notes.txt`.
    >> mkdir devops_workspace
    >> touch project_notes.txt
  - Set permissions:
    - **Owner can edit**, **group can read**, **others have no access**.
    >> chmod 240 project_notes.txt
  - Use `ls -l` to verify permissions.

---

### **3️⃣ Log File Analysis with AWK, Grep & Sed**

- **Task:**  
  - **Download the log file** from the repository.
  - **Extract insights using commands:**
    - Use `grep` to find all occurrences of the word **"error"**.
      >>  grep -c -w "error" file.txt ( -c counts the number of matches ) ( -w option ensures that only whole words are matched ) 
    - Use `awk` to extract **timestamps and log levels**.
      >> awk '{print $1, $2}' file.txt
    - Use `sed` to replace all IP addresses with **[REDACTED]** for security.
      >> 
  - **Bonus:** Find the most frequent log entry using `awk` or `sort | uniq -c | sort -nr | head -10`.
          >> sort|uniq -c|head -10 file.txt

---

### **4️⃣ Volume Management & Disk Usage**
- **Task:**  
  - Create a directory `/mnt/devops_data`.
  - Mount a new volume (or loop device for local practice).
  - Verify using `df -h` and `mount | grep devops_data`.

---

### **5️⃣ Process Management & Monitoring**
- **Task:**  
  - Start a background process (`ping google.com > ping_test.log &`).
  - Use `ps`, `top`, and `htop` to monitor it.
  - Kill the process and verify it's gone.

---

### **6️⃣ Automate Backups with Shell Scripting**
- **Task:**  
  - Write a shell script to back up `/devops_workspace` as `backup_$(date +%F).tar.gz`.
  - Save it in `/backups` and schedule it using `cron`.
  - Make the script display a success message in **green text** using `echo -e`.

---

## 🎯 Bonus Tasks (Optional 🚀)
1. Find the **top 5 most common log messages** in `Linux_2k.log` using `awk` and `sort`.
2. Use `find` to list **all files modified in the last 7 days**.
3. Write a script that extracts and displays only **ERROR and WARNING logs** from `Linux_2k.log`.

---
