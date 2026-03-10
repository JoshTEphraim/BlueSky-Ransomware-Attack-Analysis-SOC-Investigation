# Investigation Timeline

## Phase 1 – Reconnaissance

Network traffic analysis revealed scanning activity from an external IP address targeting services on the victim machine.

Suspicious source IP:
`87.96.21.84`

Ports scanned included:
80 (HTTP)
443 (HTTPS)
445 (SMB)

This suggests the attacker was identifying exposed services for exploitation.

---

## Phase 2 – Initial Access

The attacker targeted a Microsoft SQL Server instance using compromised credentials.

Evidence shows login attempts against the **sa** account.

After successful authentication, the attacker gained the ability to execute commands remotely.

---

## Phase 3 – Command Execution

The attacker enabled the SQL Server feature **xp_cmdshell** which allows system command execution.

Command observed:

`EXEC sp_configure 'xp_cmdshell', 1`
`RECONFIGURE`

This allowed the attacker to execute OS-level commands from SQL Server.

---

## Phase 4 – Payload Download

The attacker downloaded malicious PowerShell scripts from remote infrastructure.

Example URL:

`hxxp[:]//87.96.21.84/del.ps1`

The script was used to stage further malicious activity.

---

## Phase 5 – Defense Evasion

Security controls were disabled to avoid detection.

Windows Defender services were stopped before malware execution.

---

## Phase 6 – Credential Dumping

Credential dumping tools were executed to extract password hashes.

PowerShell script used:

`Invoke-PowerDump.ps1`

Extracted hashes were saved to:

`hashes.txt`

---

## Phase 7 – Persistence

A scheduled task was created to maintain access.

Command used:

`schtasks /create`

This allowed the attacker to regain execution after system reboot.

---

## Phase 8 – Ransomware Deployment

The final stage involved deploying BlueSky ransomware.

Files were encrypted and renamed with the extension:

`.bluesky`

A ransom note was dropped on the system.
