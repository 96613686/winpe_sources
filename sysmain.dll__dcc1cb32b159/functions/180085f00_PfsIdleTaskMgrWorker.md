# PfsIdleTaskMgrWorker

- ea: `0x180085f00`
- end: `0x180085fba`
- name: `PfsIdleTaskMgrWorker`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x18003c14c`
- `0x180085f00`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180085f4a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180085f4a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180085fa0`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180085fa0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180085f2c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180085f2c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180085f6c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180085f7c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180085f6c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180085f7c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180085f86`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180085f86`

## pseudocode

```c

```
