# WctCreateSystemSnapshot(utl::unique_ptr<_SYSTEM_PROCESS_INFORMATION,tlx::generic_delete<_SYSTEM_PROCESS_INFORMATION,tlx::operator_delete_deallocate>> *)

- ea: `0x180061c48`
- end: `0x180061d80`
- name: `?WctCreateSystemSnapshot@@YAKPEAV?$unique_ptr@U_SYSTEM_PROCESS_INFORMATION@@U?$generic_delete@U_SYSTEM_PROCESS_INFORMATION@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@@Z`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180060970`
- `0x18006180c`

## callees

- `0x18001e0d0`
- `0x18002e94c`
- `0x180061c48`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061c74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061cc7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061c74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180061cc7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061cee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180061cee`
- `ntdll!NtQuerySystemInformation` at `0x180061c97`
- `ntdll!NtQuerySystemInformation` at `0x180061c97`
- `ntdll!RtlNtStatusToDosError` at `0x180061d4d`
- `ntdll!RtlNtStatusToDosError` at `0x180061d4d`

## pseudocode

```c

```
