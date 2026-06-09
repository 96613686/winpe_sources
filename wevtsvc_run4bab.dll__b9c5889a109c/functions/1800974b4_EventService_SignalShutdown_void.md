# EventService::SignalShutdown(void)

- ea: `0x1800974b4`
- end: `0x18009761c`
- name: `?SignalShutdown@EventService@@QEAAXXZ`
- size: `360`
- prototype: `void __fastcall(PSRWLOCK SRWLock)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18009340c`
- `0x18009e314`

## callees

- `0x18000bf10`
- `0x180019d28`
- `0x180047ee0`
- `0x18004ac80`
- `0x1800974b4`
- `0x180097624`
- `0x1800a75e8`
- `0x1800a7814`
- `0x1800c6254`
- `0x1800c6c78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800974c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009751e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800974c9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009751e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800974dd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800974dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800974e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800975e1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800974e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800975e1`

## pseudocode

```c

```
