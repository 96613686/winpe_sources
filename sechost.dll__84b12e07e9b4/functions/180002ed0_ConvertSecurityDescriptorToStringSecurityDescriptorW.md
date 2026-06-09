# ConvertSecurityDescriptorToStringSecurityDescriptorW

- ea: `0x180002ed0`
- end: `0x180002f8b`
- name: `ConvertSecurityDescriptorToStringSecurityDescriptorW`
- size: `187`
- prototype: `BOOL __stdcall(PSECURITY_DESCRIPTOR SecurityDescriptor, DWORD RequestedStringSDRevision, SECURITY_INFORMATION SecurityInformation, LPWSTR *StringSecurityDescriptor, PULONG StringSecurityDescriptorLen)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ed0`
- `0x180004260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002f7c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002f52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002f52`

## pseudocode

```c

```
