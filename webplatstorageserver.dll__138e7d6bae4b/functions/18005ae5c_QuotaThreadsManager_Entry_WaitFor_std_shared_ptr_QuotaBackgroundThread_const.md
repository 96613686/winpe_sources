# QuotaThreadsManager::Entry::WaitFor(std::shared_ptr<QuotaBackgroundThread> const &)

- ea: `0x18005ae5c`
- end: `0x18005aefc`
- name: `?WaitFor@Entry@QuotaThreadsManager@@QEAAXAEBV?$shared_ptr@VQuotaBackgroundThread@@@std@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180070ce4`
- `0x180071c60`

## callees

- `0x18005ae5c`
- `0x180061c90`
- `0x180066010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005ae71`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18005ae71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005aef5`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18005aec6`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18005aec6`

## string_xrefs

- `0x18005ae8e`: `onecoreuap\inetcore\webplatstorageserver\clientmanager\quotathreadsmanager.cxx`
- `0x18005aed0`: `onecoreuap\inetcore\webplatstorageserver\clientmanager\quotathreadsmanager.cxx`

## pseudocode

```c

```
