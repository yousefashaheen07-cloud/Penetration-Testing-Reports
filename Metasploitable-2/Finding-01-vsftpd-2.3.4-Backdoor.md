# Finding 01 — vsftpd 2.3.4 Backdoor

## Target
Metasploitable 2

## IP Address
192.168.116.129

## Port
21/TCP

## Service
FTP

## Version
vsftpd 2.3.4

## Vulnerability
vsftpd 2.3.4 Backdoor Command Execution

## CVE
CVE-2011-2523

## Severity
Critical

## Discovery

Nmap service enumeration identified FTP running on port 21
with vsftpd version 2.3.4.

The scan also identified that Anonymous FTP login was allowed.

## Vulnerability Verification

Searchsploit was used to verify whether a known exploit
was associated with vsftpd 2.3.4.

The search returned:

vsftpd 2.3.4 - Backdoor Command Execution

## Exploitation

The vulnerability was tested in the Metasploitable 2 lab
using the following Metasploit module:

exploit/unix/ftp/vsftpd_234_backdoor

The exploitation was successful.

## Result

A shell session was obtained on the target.

The session was subsequently upgraded to a Meterpreter
session.

The Meterpreter session reported the server username as:

root

The target system was identified as:

Ubuntu 8.04
Linux 2.6.24-16-server
i686 architecture

## Impact

Successful exploitation of the backdoor can provide remote
command execution on the affected system.

Because the obtained session had root privileges in this
lab environment, an attacker could potentially gain complete
control over the affected system.

## Evidence

### Evidence 1 — Service Enumeration
Nmap identified:

21/tcp open ftp vsftpd 2.3.4
<img width="471" height="320" alt="{FBA9A537-54A9-422E-9ABF-58D4060D8B99}" src="https://github.com/user-attachments/assets/1e872de9-3a70-4fe6-9f22-7ff8ccaeb6fd" />


### Evidence 2 — Exploit Identification
Searchsploit identified the known vsftpd 2.3.4 backdoor.
<img width="1366" height="768" alt="{2627B0DB-B93E-4192-89BB-8473DD71DE44}" src="https://github.com/user-attachments/assets/fe59a9ed-052a-467b-819f-3047d8cfe5cb" />


### Evidence 3 — Successful Exploitation
Metasploit successfully established a shell/Meterpreter
session with root privileges.
<img width="1198" height="537" alt="d36c7e26-9079-474a-90ac-5c50eef93711" src="https://github.com/user-attachments/assets/3ce1ccc9-54dd-40b7-9299-10e948c8d43b" />


## Remediation

1. Remove the vulnerable vsftpd 2.3.4 installation.

2. Replace it with a trusted, patched, and supported version
   of vsftpd obtained from a trusted software repository.

3. Do not use a compromised or untrusted vsftpd package.

4. Disable Anonymous FTP access unless it is explicitly required.

5. Restrict access to the FTP service using firewall rules
   and network access controls.

6. If the affected system were a real production system,
   investigate it for compromise and rotate credentials or
   secrets that may have been exposed.

## References

CVE-2011-2523:
https://www.cve.org/CVERecord?id=CVE-2011-2523

## Lab Environment

Metasploitable 2
