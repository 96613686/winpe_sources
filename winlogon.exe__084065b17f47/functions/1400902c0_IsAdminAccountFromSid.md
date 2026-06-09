# IsAdminAccountFromSid

- ea: `0x1400902c0`
- end: `0x140090403`
- name: `IsAdminAccountFromSid`
- size: `323`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14008f814`

## callees

- `0x1400057f4`
- `0x140053720`
- `0x1400544e0`
- `0x1400902c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140090381`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140090353`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x140090353`
- `samcli!NetUserGetInfo` at `0x1400903bd`
- `samcli!NetUserGetInfo` at `0x1400903bd`
- `netutils!NetApiBufferFree` at `0x1400903db`
- `netutils!NetApiBufferFree` at `0x1400903db`

## pseudocode

```c

```
