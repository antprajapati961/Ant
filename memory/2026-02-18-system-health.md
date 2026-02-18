# System Health Report - 2026-02-18

## Security Findings

### Critical Issues
- **UFW Firewall**: Not installed. No host-level firewall protection active.
- **fail2ban**: Not installed. No intrusion prevention system.

### SSH Configuration
- `PermitRootLogin`: Commented out (using default: prohibit-password) — acceptable
- `PasswordAuthentication`: Commented out (using default: yes) — should be explicitly set to `no` if using key-based auth only

### Positive
- **unattended-upgrades**: Installed and enabled — security patches auto-applied ✓

### Service Bloat
Running unnecessary services that increase attack surface:
- gdm (GNOME Display Manager) — not needed on server
- cups, cups-browsed (printing) — not needed
- colord (color management) — not needed
- avahi-daemon (mDNS) — not needed
- ModemManager — not needed
- fwupd (firmware updates) — consider if needed

## Resource Status
- **Disk**: 41% used (69G available) — healthy
- **Memory**: 2.9Gi/15Gi used — healthy
- **Swap**: 0B — no swap configured

## Recommendations
1. Install and enable UFW: `sudo apt install ufw && sudo ufw enable`
2. Install fail2ban: `sudo apt install fail2ban`
3. Disable unnecessary services: `sudo systemctl disable gdm cups avahi-daemon ModemManager`
4. Explicitly set `PasswordAuthentication no` in `/etc/ssh/sshd_config` if using key-only auth
5. Configure UFW rules for SSH (port 22) before enabling
