# CVdsService::GetDiskObjectWrapper(_GUID,IUnknown * *)

- ea: `0x1400392a0`
- end: `0x140039726`
- name: `?GetDiskObjectWrapper@CVdsService@@QEAAJU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `1158`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct _GUID *__struct_ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140001980`

## callees

- `0x14000d6e0`
- `0x14000dd3c`
- `0x1400392a0`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400396dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400396ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400396dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400396ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039546`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039558`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039546`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039558`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14003956e`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x14003956e`
- `vdsutil!VdsTraceEx` at `0x1400393e0`
- `vdsutil!VdsTraceEx` at `0x140039496`
- `vdsutil!VdsTraceEx` at `0x140039621`
- `vdsutil!VdsTraceEx` at `0x1400396b5`
- `vdsutil!VdsTraceEx` at `0x1400393e0`
- `vdsutil!VdsTraceEx` at `0x140039496`
- `vdsutil!VdsTraceEx` at `0x140039621`
- `vdsutil!VdsTraceEx` at `0x1400396b5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039309`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039309`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400396f7`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400396f7`

## string_xrefs

- `0x1400392f5`: `CVdsService::GetDiskObjectWrapper()`

## pseudocode

```c

```
