# CVdsService::GetHbaPort(_GUID,IUnknown * *)

- ea: `0x14003972c`
- end: `0x140039834`
- name: `?GetHbaPort@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `264`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000e920`

## callees

- `0x14003972c`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039812`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140039812`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039763`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140039763`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140039776`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140039776`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140039791`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x140039791`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x1400397be`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x1400397be`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x1400397e2`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x1400397e2`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039755`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140039755`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003981e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003981e`

## string_xrefs

- `0x140039744`: `CVdsService::GetHbaPort()`

## pseudocode

```c

```
