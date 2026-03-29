# TryHackMe - Linux Fundamentals Part 1

## 🎯 Objective
Learn basic Linux commands and how to interact with the filesystem

---

## 💻 Commands Used

whoami
- ls
- cat
- cd
- pwd
- grep

## 🧠 What I Learned
How to check current user using whoami
How to list files using ls
How to read file contents using cat
How to navigate directories using cd
How to find files or patterns using grep

## 🧪 What I Did
Checked current user in the system
Explored directories and files
Opened a file and read its content
Searched for specific text inside log file

## 📌 Result
Able to navigate Linux system
Able to find and read files
Understand basic command usage

## 🔥 Security Insight
Multiple failed login attempts in logs may indicate brute force attack
Log files are important for detecting suspicious activity


whoami 
- Knowing the current user helps identify privilege level
- Unexpected user may indicate unauthorized access

ls
- Listing files may reveal sensitive data or hidden files
- Attackers often search for configuration or credential files

cat
- Used to read file contents, including sensitive information
- Important for analyzing logs and detecting suspicious activity

find
- Listing files may reveal sensitive data or hidden files
- Attackers often search for configuration or credential files

Grep
- Used to search logs for suspicious patterns
- Useful for detecting brute force or anomalies

&
- Runs process in background
- Suspicious background tasks may indicate malware
