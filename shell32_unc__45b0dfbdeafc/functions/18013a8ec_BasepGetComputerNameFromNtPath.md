# BasepGetComputerNameFromNtPath

- ea: `0x18013a8ec`
- end: `0x18013adee`
- name: `BasepGetComputerNameFromNtPath`
- size: `1282`
- prototype: `__int64 __fastcall(STRING *String2, HANDLE FileHandle, void *, LPDWORD nSize)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18013a5b4`

## callees

- `0x18013a8ec`
- `0x180249490`
- `0x18024a524`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18013aa80`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18013aa80`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013aa50`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013aac0`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013aae4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013ab08`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013ab2c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013aa50`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013aac0`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013aae4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013ab08`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18013ab2c`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18013aa22`
- `api-ms-win-core-file-l1-1-0!QueryDosDeviceW` at `0x18013aa22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013aa32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013aa32`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18013adb1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18013adb1`
- `ntdll!RtlInitUnicodeString` at `0x18013a972`
- `ntdll!RtlInitUnicodeString` at `0x18013abcc`
- `ntdll!RtlInitUnicodeString` at `0x18013a972`
- `ntdll!RtlInitUnicodeString` at `0x18013abcc`
- `ntdll!RtlPrefixString` at `0x18013a989`
- `ntdll!RtlPrefixString` at `0x18013a9d2`
- `ntdll!RtlPrefixString` at `0x18013a989`
- `ntdll!RtlPrefixString` at `0x18013a9d2`
- `ntdll!NtQueryInformationFile` at `0x18013ab61`
- `ntdll!NtQueryInformationFile` at `0x18013ab61`
- `ntdll!RtlNtStatusToDosError` at `0x18013ab73`
- `ntdll!RtlNtStatusToDosError` at `0x18013ab73`
- `ntdll!NtCreateFile` at `0x18013ac3b`
- `ntdll!NtCreateFile` at `0x18013ac3b`
- `ntdll!NtClose` at `0x18013ac5d`
- `ntdll!NtClose` at `0x18013acc0`
- `ntdll!NtClose` at `0x18013ac5d`
- `ntdll!NtClose` at `0x18013acc0`
- `ntdll!NtFsControlFile` at `0x18013acac`
- `ntdll!NtFsControlFile` at `0x18013acac`

## pseudocode

```c

```
