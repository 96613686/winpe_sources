# LookupAccountNameLocalA

- ea: `0x180018940`
- end: `0x180018a73`
- name: `LookupAccountNameLocalA`
- size: `307`
- prototype: `BOOL __stdcall(LPCSTR lpAccountName, PSID Sid, LPDWORD cbSid, LPSTR ReferencedDomainName, LPDWORD cchReferencedDomainName, PSID_NAME_USE peUse)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000ce20`
- `0x18000de70`
- `0x180018940`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800189fe`
- `ntdll!RtlInitUnicodeString` at `0x1800189fe`
- `ntdll!RtlInitAnsiString` at `0x180018989`
- `ntdll!RtlInitAnsiString` at `0x180018989`
- `ntdll!RtlFreeUnicodeString` at `0x180018a4f`
- `ntdll!RtlFreeUnicodeString` at `0x180018a4f`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001899a`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001899a`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180018a2c`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180018a2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800189b4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800189b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018a3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018a3e`

## pseudocode

```c

```
