# System Hardening

This section lists the fixes for the vulnerabilities found in this test.

## 1. Apply Security Patches
- Update the operating system and all installed packages.
- Remove or replace the vsftpd 2.3.4 service.

## 2. Configure the Firewall
- Allow only the ports the server needs.
- Example rule to block FTP from everywhere except a trusted host:
  `sudo iptables -A INPUT -p tcp --dport 21 -s 192.168.56.10 -j ACCEPT`
  `sudo iptables -A INPUT -p tcp --dport 21 -j DROP`

## 3. Disable Unused Services
- Stop and disable FTP if it is not needed:
  `sudo service vsftpd stop`
  `sudo update-rc.d vsftpd disable`

## 4. Protect Sensitive Files
- Keep `/etc/shadow` readable only by root.
- Remove sudo rights from accounts that do not need them.
