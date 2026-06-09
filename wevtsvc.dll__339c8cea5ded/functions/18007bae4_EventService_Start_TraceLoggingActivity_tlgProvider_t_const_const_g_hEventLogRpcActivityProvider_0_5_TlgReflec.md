# EventService::Start(TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider> &)

- ea: `0x18007bae4`
- end: `0x18007bc5b`
- name: `?Start@EventService@@QEAAXAEAV?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18009daf0`

## callees

- `0x180001008`
- `0x180033ae0`
- `0x180064854`
- `0x18007bae4`
- `0x180092ee4`
- `0x18009340c`
- `0x1800982f4`
- `0x18009aee0`
- `0x1800ab458`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007bbba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007bbba`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007bbed`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007bbed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007bc27`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007bc27`

## pseudocode

```c

```
