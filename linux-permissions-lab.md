f#  Linux File Permissions & Access Control
**Focus:** IT Support | System Administration | Cybersecurity Fundamentals
**Environment:** Linux Command Line (Cisvo Linux Essentials / Ubuntu) 

## 1. Objective
Demonstrated foundational system administration and security hardening by configuring strict file ownership, creating administrative user groups, and applying least priviledge permission flags to protect sensitive directory contents.

## 2. Implementation Stops
- **Verfied Curret Permission:** Checked existing file ownership and access rights using: 
- ls -la /var/secure_data

- **Created a Dedicated Security Group:**
- Isolated authorized administratve users by creating a new group:
-
- sudo groupadd sec-admins

- **Assigned User Membership:**
- Added the authorized operator account to the administrative group:

- sudo usermod -aG sec_admins jfutrell

- **Applied Hardened Ownership & Permissions:**
- Restricted diretory access so only root and members of the sec_admins group could read or execute file

- sudo chown root:sec_admins /var/secure_data
- chmod 750 /var/secure_data

- ## 3. Verification & Troubleshooting

- **Verification:** Switched to an unpriviledged test account and attempted to access the directory, confirming that access was correctly blocked (Permission Denied),
- **Troubleshooting Note:** Initially encountered a syntax typo in the group name during assignment. Resolved by inspection active groups with cat /etc/group and correcting the flag.

- ## 4. Security Takeaway
- Enforcing the Principle of Least Privilege (PoLP)
- prevents unauthorized users from viewing or modifying critical system directories, effectively limiting lateral movement in the event of an account compromise.
- 

