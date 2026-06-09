# PfsVolumeGetInfo

- ea: `0x180086fec`
- end: `0x180087246`
- name: `PfsVolumeGetInfo`
- size: `602`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x18006067c`
- `0x1800b1490`

## callees

- `0x180086fec`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180087153`
- `msvcrt!_wcsnicmp` at `0x180087153`
- `ntdll!NtCreateFile` at `0x1800870f0`
- `ntdll!NtCreateFile` at `0x1800870f0`
- `ntdll!NtQueryVolumeInformationFile` at `0x18008713a`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800871e4`
- `ntdll!NtQueryVolumeInformationFile` at `0x18008713a`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800871e4`
- `ntdll!RtlInitUnicodeString` at `0x180087077`
- `ntdll!RtlInitUnicodeString` at `0x180087077`
- `ntdll!RtlNtStatusToDosError` at `0x1800870fc`
- `ntdll!RtlNtStatusToDosError` at `0x1800870fc`
- `ntdll!NtClose` at `0x18008721f`
- `ntdll!NtClose` at `0x18008721f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18008719f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18008719f`

## pseudocode

```c

```
