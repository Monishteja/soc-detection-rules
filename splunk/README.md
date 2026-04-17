# Credential Stuffing Detection

## MITRE ATT&CK Mapping
- **Tactic:** Initial Access
- **Technique:** T1078.001 - Valid Accounts: Default Accounts

## Detection Logic
This rule identifies credential stuffing attacks by detecting:
1. Multiple failed login attempts (>10) within 5-minute window
2. From multiple source IPs (>3) targeting same user
3. Risk scoring based on attempt volume and IP diversity

## Tuning Recommendations
- Adjust `failed_logins > 10` threshold based on your environment
- Whitelist known VPN IP ranges to reduce false positives
- Add `src_ip NOT IN (vpn_lookup)` for environments with remote workers

## Test Data
