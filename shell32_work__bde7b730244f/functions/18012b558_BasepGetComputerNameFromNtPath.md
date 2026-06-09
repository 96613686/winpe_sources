# BasepGetComputerNameFromNtPath

- ea: `0x18012b558`
- end: `0x18012b9e7`
- name: `BasepGetComputerNameFromNtPath`
- size: `1167`
- prototype: `__int64 __fastcall(STRING *String2, HANDLE FileHandle, void *, LPDWORD nSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18012b264`

## callees

- `0x18012b558`
- `0x180233280`
- `0x1802342e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18012b6c8`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18012b6c8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b69e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b702`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b720`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b73e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b75c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b69e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b702`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b720`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b73e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18012b75c`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18012b67c`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18012b67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b686`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18012b9b1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18012b9b1`
- `ntdll!RtlInitUnicodeString` at `0x18012b5de`
- `ntdll!RtlInitUnicodeString` at `0x18012b7ea`
- `ntdll!RtlInitUnicodeString` at `0x18012b5de`
- `ntdll!RtlInitUnicodeString` at `0x18012b7ea`
- `ntdll!RtlPrefixString` at `0x18012b5ef`
- `ntdll!RtlPrefixString` at `0x18012b632`
- `ntdll!RtlPrefixString` at `0x18012b5ef`
- `ntdll!RtlPrefixString` at `0x18012b632`
- `ntdll!NtQueryInformationFile` at `0x18012b78b`
- `ntdll!NtQueryInformationFile` at `0x18012b78b`
- `ntdll!RtlNtStatusToDosError` at `0x18012b797`
- `ntdll!RtlNtStatusToDosError` at `0x18012b797`
- `ntdll!NtCreateFile` at `0x18012b853`
- `ntdll!NtCreateFile` at `0x18012b853`
- `ntdll!NtClose` at `0x18012b86f`
- `ntdll!NtClose` at `0x18012b8c6`
- `ntdll!NtClose` at `0x18012b86f`
- `ntdll!NtClose` at `0x18012b8c6`
- `ntdll!NtFsControlFile` at `0x18012b8b8`
- `ntdll!NtFsControlFile` at `0x18012b8b8`

## pseudocode

```c

```
