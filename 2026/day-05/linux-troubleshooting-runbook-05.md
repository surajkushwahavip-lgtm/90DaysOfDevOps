# Day 05 - Linux Troubleshooting Runbook

## Target Service
SSH (sshd)

## Commands & Findings

### Environment Check
```bash
uname -a
cat /etc/os-release
```
- Verified Ubuntu 24.04.4 LTS environment.

### Filesystem Check
```bash
mkdir -p /tmp/runbook-demo
ls -l /tmp/runbook-demo
```
- Test directory created successfully.
- Filesystem working as expected.

### CPU & Memory Check
```bash
ps -o pid,pcpu,pmem,comm -p $(pgrep sshd)
free -h
```
- SSH process running normally.
- Memory usage within healthy limits.

### Disk Check
```bash
df -h
du -sh /var/log
```
- Sufficient disk space available.
- Log directory size is normal.

### Network Check
```bash
ss -tulpn
```
- Active services are listening correctly.

### Log Review
```bash
journalctl -u ssh -n 50
journalctl -u ssh -f
```
- Reviewed SSH logs.
- No critical errors found.
- SSH service restarted successfully and listening on port 22.

## Quick Findings
✅ SSH service healthy  
✅ CPU & Memory usage normal  
✅ Disk space sufficient  
✅ No critical log errors

## If This Worsens
1. Check detailed logs using `journalctl -u ssh -xe`
2. Verify SSH port using `ss -tulpn | grep :22`
3. Collect advanced diagnostics using `strace`
