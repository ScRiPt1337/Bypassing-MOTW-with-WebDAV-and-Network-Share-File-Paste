Bypassing MOTW with File Paste Behavior in Network Shares

Overview

When pasting a file over an existing .lnk or .exe file in a network share (such as WebDAV or SMB), Windows executes the target file without issuing any Mark of the Web (MOTW) warnings, bypassing security prompts. This behavior is significant because it can be exploited for automatic execution of potentially malicious payloads.

Key Findings

1. MOTW Bypass: Normally, .lnk and .exe files from network shares trigger MOTW warnings. However, when a file is pasted onto an existing .lnk or .exe, Windows executes the file without warnings.


2. WebDAV and SMB Shares: Both WebDAV and SMB shares apply MOTW, but pasting a file over .lnk or .exe bypasses MOTW and leads to execution.


3. Automatic Execution: Simply pasting a file over an existing .lnk or .exe causes Windows to automatically execute the file, which can be exploited for malicious purposes.



Security Implications

Attackers can exploit this behavior by placing malicious .lnk or .exe files in shared folders and tricking users into pasting files over them, resulting in automatic execution.

Red teamers can use this to simulate stealthy payload delivery.


Mitigation

1. Restrict file execution from network shares using AppLocker or GPO.


2. Educate users on the risks of file paste operations in shared folders.


3. Secure WebDAV and SMB shares and monitor for unusual file activity.




---

This behavior highlights a potential security risk in shared environments, and organizations should take steps to restrict execution from network shares to prevent exploitation.

