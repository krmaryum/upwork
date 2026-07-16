# Syslog-ng Operations Runbook

## 1. Purpose

This runbook provides routine checks and safe operational procedures. Replace placeholders with final client values during handover.

## 2. Daily Health Check

```bash
sudo systemctl is-active syslog-ng
sudo systemctl status syslog-ng
sudo journalctl -u syslog-ng --since today --no-pager
sudo ss -lntup
df -h
```

Verify:

- Service is active.
- Approved ports are listening.
- No repeated errors appear in the service journal.
- The log filesystem has acceptable free space.
- Expected sources are sending data.
- Dashboard and activity timestamps are updating.

## 3. Validate Configuration

Before a restart:

```bash
sudo syslog-ng --syntax-only
```

Do not restart when syntax validation fails.

## 4. Controlled Restart

1. Record current service status.
2. Confirm an approved change window if required.
3. Validate syntax.
4. Restart the service.
5. Confirm active status.
6. Confirm listeners.
7. Send or observe a test message.
8. Confirm the correct destination file.

```bash
sudo syslog-ng --syntax-only
sudo systemctl restart syslog-ng
sudo systemctl status syslog-ng
sudo ss -lntup
```

## 5. Locate a Source’s Logs

Use the approved source inventory to identify:

- Source IP or hostname
- Listener port
- Date
- Active or archive location

Example pattern:

```text
/var/log/remote/active/port-PORT/SOURCE_IP/YYYY-MM-DD.log
```

## 6. Check Recent Data

Use non-destructive commands and protect sensitive content.

```bash
sudo find /var/log/remote -type f -mmin -10 -ls
sudo du -sh /var/log/remote
```

Avoid copying client log content into tickets or screenshots unless approved.

## 7. Check Source Activity

Review the dashboard or approved activity query for:

- Source IP
- Port and protocol
- Last-received timestamp
- Message count
- Current status

Investigate a silent source using the troubleshooting guide.

## 8. Check Rotation and Archives

Verify:

- Active logs continue growing.
- Rotated logs have the expected date and name.
- Compression completes.
- Archives are readable.
- No unexpected files match the deletion policy.

Never manually delete production logs without an approved request and verified backup/retention policy.

## 9. Disk-Usage Response

### Warning level

1. Identify the growing filesystem.
2. Identify the largest source/path.
3. Confirm whether rotation is running.
4. Confirm compression is succeeding.
5. Review unexpected traffic spikes.
6. Notify the client before changing retention.

### Critical level

1. Escalate immediately.
2. Preserve service and incident evidence.
3. Do not delete logs randomly.
4. Follow the approved emergency storage procedure.
5. Add temporary approved storage or move approved archives if the runbook permits.

## 10. Configuration Backup

Back up:

- Main syslog-ng configuration
- Included configuration fragments
- Rotation policy
- Activity tracking configuration
- Dashboard exports
- Alert rules
- Firewall/SELinux change records

Store backups in the client-approved protected location.

## 11. Escalation Information

| Role | Contact | Responsibility |
|---|---|---|
| RHEL administrator | To be completed | OS, service, storage, SELinux |
| Network team | To be completed | Routes and firewall |
| Application owner | To be completed | Source configuration |
| Monitoring team | To be completed | Dashboard and alerts |
| Security team | To be completed | TLS, access, and audit |

