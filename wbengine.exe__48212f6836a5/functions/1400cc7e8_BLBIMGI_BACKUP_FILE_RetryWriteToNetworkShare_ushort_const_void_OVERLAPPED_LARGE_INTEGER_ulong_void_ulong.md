# BLBIMGI_BACKUP_FILE::RetryWriteToNetworkShare(ushort const *,void *,_OVERLAPPED *,_LARGE_INTEGER *,ulong,void * *,ulong *)

- ea: `0x1400cc7e8`
- end: `0x1400ccbd1`
- name: `?RetryWriteToNetworkShare@BLBIMGI_BACKUP_FILE@@QEAA?AW4_BLBIMG_RESULT_CODE@@PEBGPEAXPEAU_OVERLAPPED@@PEAT_LARGE_INTEGER@@KPEAPEAXPEAK@Z`
- size: `1001`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1400bbdd0`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000bb4c`
- `0x14003c434`
- `0x1400cc7e8`
- `0x1400ce820`
- `0x1400cf7c8`
- `0x1400cfa08`

## import_xrefs

- `KERNEL32!SleepEx` at `0x1400cc944`
- `KERNEL32!SleepEx` at `0x1400cc944`
- `KERNEL32!GetOverlappedResult` at `0x1400cca27`
- `KERNEL32!GetOverlappedResult` at `0x1400cca27`
- `KERNEL32!CloseHandle` at `0x1400cc955`
- `KERNEL32!CloseHandle` at `0x1400cc955`
- `KERNEL32!GetLastError` at `0x1400cca31`
- `KERNEL32!GetLastError` at `0x1400cca31`
- `ntdll!RtlNtStatusToDosError` at `0x1400cc9b5`
- `ntdll!RtlNtStatusToDosError` at `0x1400cc9b5`
- `ntdll!NtCreateFile` at `0x1400cc9a9`
- `ntdll!NtCreateFile` at `0x1400cc9a9`
- `ntdll!RtlFreeHeap` at `0x1400ccb81`
- `ntdll!RtlFreeHeap` at `0x1400ccb81`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400cc8ca`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1400cc8ca`

## string_xrefs

- `0x1400cc870`: `_isCompactForm == FALSE`

## pseudocode

```c

```
