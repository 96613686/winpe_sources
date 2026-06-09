# CVdsService::GetInitiatorAdapter(_GUID,IUnknown * *)

- ea: `0x14002918c`
- end: `0x1400292df`
- name: `?GetInitiatorAdapter@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `339`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000e920`

## callees

- `0x14002918c`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140029292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400292b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140029292`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400292b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400291eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400291eb`
- `vdsutil!VdsTraceEx` at `0x1400291cd`
- `vdsutil!VdsTraceEx` at `0x1400292ab`
- `vdsutil!VdsTraceEx` at `0x1400291cd`
- `vdsutil!VdsTraceEx` at `0x1400292ab`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x1400291fe`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x1400291fe`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140029219`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140029219`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140029246`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x140029246`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14002926a`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14002926a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400291ad`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400291ad`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400292c9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400292c9`

## string_xrefs

- `0x14002929c`: `CVdsService::GetInitiatorAdapter(), 2`
- `0x14002919c`: `CVdsService::GetInitiatorAdapter()`
- `0x1400291c1`: `CVdsService::GetInitiatorAdapter(), 1`

## pseudocode

```c

```
