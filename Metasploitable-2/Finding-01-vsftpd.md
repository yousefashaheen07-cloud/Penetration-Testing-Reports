# Finding 01 — vsftpd 2.3.4 Backdoor

## Target
Metasploitable 2

## Port
21/TCP

## Service
FTP

## Version
vsftpd 2.3.4

## Vulnerability
vsftpd 2.3.4 Backdoor

## CVE
CVE-2011-2523

## Severity
Critical

## Discovery
During service enumeration, FTP was identified on port 21,
and the service version was identified as vsftpd 2.3.4.

## Metasploit Module
exploit/unix/ftp/vsftpd_234_backdoor

## Exploitation
The vulnerable service was tested using the appropriate
Metasploit module within the Metasploitable 2 lab.

## Result
Successful exploitation may provide a command shell
on the target system.

## Evidence
Screenshots and command output can be added here.

## Remediation
Upgrade or replace the vulnerable version of vsftpd
with a patched and supported version.

## Lab Environment
Metasploitable 2
