# SbpParseSignatureDatabase

- ea: `0x1800385a0`
- end: `0x180038761`
- name: `SbpParseSignatureDatabase`
- size: `449`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, LPGUID VendorGuid@<rdx>, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800377a0`

## callees

- `0x1800383e4`
- `0x1800385a0`
- `0x180038768`

## import_xrefs

- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180038628`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180038677`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180038628`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180038677`
- `ntdll!RtlInitUnicodeString` at `0x18003860f`
- `ntdll!RtlInitUnicodeString` at `0x18003860f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003869c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003869c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038745`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003868f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003873a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003868f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003873a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003864b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003864b`

## string_xrefs

- `0x1800385c5`: `SeSystemEnvironmentPrivilege`

## pseudocode

```c

```
