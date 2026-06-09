# CWerService::StaticPauseWorkItem(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180018950`
- end: `0x180018a23`
- name: `?StaticPauseWorkItem@CWerService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `211`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, struct _RTL_CRITICAL_SECTION *Context)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180006a80`
- `0x180011ef8`
- `0x180013df4`
- `0x180018950`
- `0x18001d7c0`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018972`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018972`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x180018a11`
- `api-ms-win-core-threadpool-l1-2-0!LeaveCriticalSectionWhenCallbackReturns` at `0x180018a11`

## pseudocode

```c

```
