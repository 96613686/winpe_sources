# CBiometricServiceProvider::GetScheduledWorkItem(std::shared_ptr<CBiometricUnit> &)

- ea: `0x18000ab6c`
- end: `0x18000ad01`
- name: `?GetScheduledWorkItem@CBiometricServiceProvider@@QEAA?AV?$shared_ptr@VCAsyncWorkItem@@@std@@AEAV?$shared_ptr@VCBiometricUnit@@@3@@Z`
- size: `405`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180047580`

## callees

- `0x180008d40`
- `0x18000ab6c`
- `0x18000ad08`
- `0x18000ad24`
- `0x18000b760`
- `0x180068f60`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ac87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000acf5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ac87`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000acf5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ac00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ac15`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ac00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000ac15`

## string_xrefs

- `0x18000aba5`: `CBiometricServiceProvider::GetScheduledWorkItem`

## pseudocode

```c

```
