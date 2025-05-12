# ELEVATION 2 - Hidden Privileges in Windows

In this lab, you will explore a corporate Windows server, identify exposed credentials, discover a key user's password through brute force, and take advantage of a misconfiguration to escalate privileges and become an administrator.

In this lab, you will learn:

- Enumeration of users and passwords in Windows environments  
- Use of `Hydra` and `rockyou.txt` for brute force attacks  
- Remote access via SSH, SMB, or WinRM  
- Privilege escalation in Windows through group misconfiguration  
- Reading flags as an administrator user  

<how-to-start>

## 🌱 How to Start This Lab

Follow these steps to begin:

1. **Download the virtual machine** from this [link](https://storage.googleapis.com/cybersecurity-machines/elevation-windows-machine.ova).
2. **Import the machine** into your preferred virtualization software (VirtualBox, VMware, etc.).
3. Once the machine is running, you're ready to start the lab!

</how-to-start>

## 📄 Instructions

You're facing a Windows server with multiple users. Your goal is to gain administrator privileges by accessing the system as the only user with a dangerous configuration.

1. **Find the IP address of the ELEVATION 2 machine.**  
   Use tools like `nmap`, `netdiscover`, or `arp-scan`.

2. **Access the shared file resource (SMB).**  
   Look for files containing visible usernames and passwords.

3. **Perform a brute force attack using Hydra.**

4. **Log in as the user with hidden privileges.**

5. **Check if you can escalate to Administrator.**

6. **Find the final flag.**

**Remember:** sometimes you don't need a technical vulnerability—just a bad security practice.

Happy hacking!
