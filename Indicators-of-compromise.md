# Indicators of Compromise (IOCs)

## Attacker Infrastructure

IP Addresses
`87.96.21.84`

Domains
None observed in the investigation

URLs
`hxxp[:]//87.96.21.84/del.ps1`

---

## Malicious Files

`del.ps1`
`Invoke-PowerDump.ps1`
`hashes.txt`

---

## File Extensions

`.bluesky`

---

## Processes

`powershell.exe`
`cmd.exe`
`winlogon.exe` (injected)

---

## Persistence Mechanisms

Scheduled Tasks
`schtasks.exe` execution

---

## Suspicious Commands

`EXEC sp_configure 'xp_cmdshell', 1`
`Invoke-PowerDump.ps1`
`powershell.exe -ExecutionPolicy Bypass`
