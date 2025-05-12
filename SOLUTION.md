# ELEVATION 2 Lab

This lab is designed to help students understand how poor password policies and improper privilege assignments can lead to full privilege escalation in a Windows environment.

In this lab, students will learn to:

- Explore shared resources (SMB) to obtain sensitive information
- Perform brute force attacks using Hydra and `rockyou.txt`
- Remotely connect as standard users
- Identify users with hidden administrator privileges
- Access sensitive files as `Administrator`


## 🖥️ Machine Specifications

- **Operating System:** Windows Server 2019 or 2022
- **Hostname:** `elevation2-lab`
- **Created Users:**

| User        | Password            | Group              |
|-------------|---------------------|---------------------|
| parker      | `?AMERICA?`         | Users               |
| valentine   | `BreakingBad90`     | Users               |
| redfield    | `5Tr0ngPaSw0rd`     | Users               |
| kennedy     | `123kennedy456`     | Users               |
| wong        | `password123`       | Administrators ✅   |

- **Sensitive file shared via SMB:** `C:\users.txt`

- **Shared directory (SMB):** `C:\` shared as `share` (public read-only)

- **Final flag:** `C:\Users\Administrator\Desktop\flag.txt`



## Expected Steps for Students

1. **Discover the server's IP**
    - Use `nmap`, `netdiscover`, or similar tools

2. **Connect via SMB**
    - Access the shared resource `\\IP\share` without authentication

3. **Obtain `users.txt`**
    - Identify complete credentials except for `wong`
    - The textual hint indicates it is a weak password

4. **Perform brute force with Hydra**
    - Target SSH (if enabled), WinRM (`5985`), or RDP (`3389`)
    - Use:
      ```bash
      hydra -l wong -P /usr/share/wordlists/rockyou.txt ssh://<IP>
      ```

5. **Access as `wong`** and verify that they have administrator privileges

6. **Read the flag on the Administrator's desktop**
    - Check if you can directly access:
      ```
      C:\Users\Administrator\Desktop\flag.txt
      ```