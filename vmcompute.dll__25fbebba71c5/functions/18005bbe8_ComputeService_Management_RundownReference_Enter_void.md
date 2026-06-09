# ComputeService::Management::RundownReference::Enter(void)

- ea: `0x18005bbe8`
- end: `0x18005bc74`
- name: `?Enter@RundownReference@Management@ComputeService@@QEAA?AV?$optional@VRundownReferenceHolder@Management@ComputeService@@@std@@XZ`
- size: `140`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `7`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004116c`
- `0x180041208`
- `0x1800412a4`
- `0x180041bc0`
- `0x180046f64`
- `0x180047c2c`
- `0x180048270`

## callees

- `0x180008c34`
- `0x180040fa0`
- `0x18005bbe8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005bbf8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005bbf8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005bc42`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005bc42`

## string_xrefs

- `0x18005bc62`: `onecore\vm\compute\shared\rundownreference\rundownreference.cpp`

## pseudocode

```c

```
