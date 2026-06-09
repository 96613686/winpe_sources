# AddUserToHandle(void *,void *,ulong)

- ea: `0x1803f8c20`
- end: `0x1803f8e8e`
- name: `?AddUserToHandle@@YAJPEAX0K@Z`
- size: `622`
- prototype: `__int64 __fastcall(HANDLE Handle, void *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1803f8e94`

## callees

- `0x180038f50`
- `0x1801884f8`
- `0x18035fa60`
- `0x1803b1f60`
- `0x1803f8c20`
- `0x1803f9610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803f8cb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1803f8cb6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f8ca2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f8daa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f8e14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f8e41`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f8ca2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f8daa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f8e14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1803f8e41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803f8dbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803f8e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803f8e55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803f8dbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803f8e28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1803f8e55`
- `ntdll!NtSetSecurityObject` at `0x1803f8de1`
- `ntdll!NtSetSecurityObject` at `0x1803f8de1`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1803f8d31`
- `ntdll!RtlCreateSecurityDescriptor` at `0x1803f8d31`
- `ntdll!NtQuerySecurityObject` at `0x1803f8c64`
- `ntdll!NtQuerySecurityObject` at `0x1803f8d02`
- `ntdll!NtQuerySecurityObject` at `0x1803f8c64`
- `ntdll!NtQuerySecurityObject` at `0x1803f8d02`

## string_xrefs

- `0x1803f8c7f`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803f8cce`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803f8d4a`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803f8d89`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1803f8df5`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c

```
