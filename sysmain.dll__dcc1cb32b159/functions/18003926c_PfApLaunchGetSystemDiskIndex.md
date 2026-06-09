# PfApLaunchGetSystemDiskIndex

- ea: `0x18003926c`
- end: `0x180039489`
- name: `PfApLaunchGetSystemDiskIndex`
- size: `541`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180038bf8`
- `0x18003f9e4`

## callees

- `0x1800076c4`
- `0x18003926c`
- `0x180062158`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800393a9`
- `ntdll!NtCreateFile` at `0x1800393a9`
- `ntdll!RtlInitUnicodeString` at `0x18003932d`
- `ntdll!RtlInitUnicodeString` at `0x18003932d`
- `ntdll!RtlNtStatusToDosError` at `0x1800393b5`
- `ntdll!RtlNtStatusToDosError` at `0x1800393b5`
- `ntdll!NtClose` at `0x18003945a`
- `ntdll!NtClose` at `0x18003945a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003941b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003941b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039442`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039442`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800393d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800393d2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180039411`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180039411`

## pseudocode

```c

```
