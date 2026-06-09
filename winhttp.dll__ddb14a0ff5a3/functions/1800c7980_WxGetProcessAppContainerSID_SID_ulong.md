# WxGetProcessAppContainerSID(_SID *,ulong)

- ea: `0x1800c7980`
- end: `0x1800c7a34`
- name: `?WxGetProcessAppContainerSID@@YAJPEAU_SID@@K@Z`
- size: `180`
- prototype: `__int64 __fastcall(PSID pDestinationSid, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180075f7c`

## callees

- `0x1800c7980`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c79fc`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c79fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c79af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7a06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c79af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c7a06`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c79a5`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800c79a5`

## pseudocode

```c

```
