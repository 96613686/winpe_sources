# ScCleanupThread(void)

- ea: `0x140065130`
- end: `0x1400652bf`
- name: `?ScCleanupThread@@YAKXZ`
- size: `399`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140066110`

## callees

- `0x140004c58`
- `0x14001f99c`
- `0x14002b304`
- `0x140036514`
- `0x1400575b0`
- `0x140065130`
- `0x14006539c`
- `0x140065528`
- `0x140065804`
- `0x140065a14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400651ca`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400651ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065247`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065263`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065247`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140065263`
- `ntdll!NtClose` at `0x140065281`
- `ntdll!NtClose` at `0x140065298`
- `ntdll!NtClose` at `0x140065281`
- `ntdll!NtClose` at `0x140065298`
- `ntdll!RtlNtStatusToDosError` at `0x140065289`
- `ntdll!RtlNtStatusToDosError` at `0x1400652a0`
- `ntdll!RtlNtStatusToDosError` at `0x140065289`
- `ntdll!RtlNtStatusToDosError` at `0x1400652a0`

## pseudocode

```c

```
