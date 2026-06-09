# LookupAccountSidLocalA

- ea: `0x18000d4e0`
- end: `0x18000d6d8`
- name: `LookupAccountSidLocalA`
- size: `504`
- prototype: `BOOL __stdcall(PSID Sid, LPSTR Name, LPDWORD cchName, LPSTR ReferencedDomainName, LPDWORD cchReferencedDomainName, PSID_NAME_USE peUse)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000d4e0`
- `0x18000d710`
- `0x18000de70`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000d5ef`
- `ntdll!RtlInitUnicodeString` at `0x18000d66f`
- `ntdll!RtlInitUnicodeString` at `0x18000d5ef`
- `ntdll!RtlInitUnicodeString` at `0x18000d66f`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000d602`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000d682`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000d602`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000d682`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d639`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d639`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d6bd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d622`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d6a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d622`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000d6a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d5c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d5c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000d6cd`

## pseudocode

```c

```
