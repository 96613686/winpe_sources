# WctSyscallCalibratorThreadProc

- ea: `0x18005f020`
- end: `0x18005f0fb`
- name: `WctSyscallCalibratorThreadProc`
- size: `219`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180004bb4`
- `0x18001fe24`
- `0x18005f020`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18005f091`
- `ntdll!NtWaitForSingleObject` at `0x18005f091`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f09d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f09d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f0b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f0b4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005f0aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18005f0aa`

## pseudocode

```c

```
