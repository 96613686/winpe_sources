# ComputeService::Management::CancellationProvider::WaitInternal(ComputeService::Management::Details::ConditionVariableWaker &,ulong)

- ea: `0x1400348e8`
- end: `0x140034b58`
- name: `?WaitInternal@CancellationProvider@Management@ComputeService@@AEBAXAEAVConditionVariableWaker@Details@23@K@Z`
- size: `624`
- prototype: `void __fastcall(ComputeService::Management::CancellationProvider *__hidden this, struct ComputeService::Management::Details::ConditionVariableWaker *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400345b0`
- `0x140034650`

## callees

- `0x140016ba8`
- `0x1400284ac`
- `0x1400341ac`
- `0x1400347f0`
- `0x1400348e8`
- `0x1400fe010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140034a2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140034a71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140034a2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140034a71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003499b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140034a46`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003499b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140034a46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140034944`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140034944`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140034917`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140034917`

## string_xrefs

- `0x140034af0`: `onecore\vm\compute\management\shared\compute\CancellationProvider.h`
- `0x140034b1b`: `onecore\vm\compute\management\shared\compute\CancellationProvider.h`
- `0x140034b46`: `onecore\vm\compute\management\shared\compute\CancellationProvider.h`

## pseudocode

```c

```
