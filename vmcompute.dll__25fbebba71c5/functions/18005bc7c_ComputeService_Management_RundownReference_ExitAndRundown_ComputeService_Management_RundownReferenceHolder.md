# ComputeService::Management::RundownReference::ExitAndRundown(ComputeService::Management::RundownReferenceHolder &&)

- ea: `0x18005bc7c`
- end: `0x18005bd04`
- name: `?ExitAndRundown@RundownReference@Management@ComputeService@@QEAAX$$QEAVRundownReferenceHolder@23@@Z`
- size: `136`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800412a4`
- `0x180041bc0`
- `0x180046f64`
- `0x180048270`

## callees

- `0x180008c34`
- `0x18005bc7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005bc90`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005bc90`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005bce1`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18005bcc1`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18005bcc1`

## string_xrefs

- `0x18005bcf2`: `onecore\vm\compute\shared\rundownreference\rundownreference.cpp`

## pseudocode

```c

```
