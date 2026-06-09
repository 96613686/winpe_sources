# CVdsService::GetLunObjectWrapper(_GUID,IUnknown * *)

- ea: `0x140039984`
- end: `0x140039d15`
- name: `?GetLunObjectWrapper@CVdsService@@QEAAJU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `913`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct _GUID *__struct_ptr, struct IUnknown **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140001980`
- `0x14003c938`

## callees

- `0x14000dd3c`
- `0x140039984`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039ccc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039cda`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039ccc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039cda`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039b40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039b52`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039b40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039b52`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140039b68`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x140039b68`
- `vdsutil!VdsTraceEx` at `0x140039aa5`
- `vdsutil!VdsTraceEx` at `0x140039c0d`
- `vdsutil!VdsTraceEx` at `0x140039cae`
- `vdsutil!VdsTraceEx` at `0x140039aa5`
- `vdsutil!VdsTraceEx` at `0x140039c0d`
- `vdsutil!VdsTraceEx` at `0x140039cae`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400399d3`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400399d3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140039ce5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140039ce5`

## string_xrefs

- `0x1400399bf`: `CVdsService::GetLunObjectWrapper()`

## pseudocode

```c

```
