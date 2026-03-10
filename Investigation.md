# Investigation Timeline

## Phase 1 – Reconnaissance

The attacker began by scanning the network to identify exposed services.

Evidence indicates scanning activity targeting multiple ports associated with web and SMB services.

---

## Phase 2 – Initial Access

The attacker leveraged compromised credentials to authenticate to a service running on the target system.

This allowed the attacker to execute commands remotely.

---

## Phase 3 – Execution

PowerShell commands were used to execute malicious scripts.

PowerShell is commonly abused by attackers because it is a trusted Windows administration tool.

---

## Phase 4 – Defense Evasion

The attacker disabled Windows Defender to avoid detection.

Security services were modified or stopped to allow malware execution.

---

## Phase 5 – Persistence

Scheduled tasks were created to maintain persistence after system reboot.

---

## Phase 6 – Credential Access

Credential dumping activity was detected, indicating the attacker attempted to extract password hashes from the system.

---

## Phase 7 – Impact

The attacker deployed **BlueSky ransomware**, encrypting victim files and leaving a ransom note.

Encrypted files were renamed with the `.bluesky` extension.
