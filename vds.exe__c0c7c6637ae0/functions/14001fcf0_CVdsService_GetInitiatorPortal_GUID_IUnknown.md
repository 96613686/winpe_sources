# CVdsService::GetInitiatorPortal(_GUID,IUnknown * *)

- ea: `0x14001fcf0`
- end: `0x14001fe2d`
- name: `?GetInitiatorPortal@CVdsService@@SAJU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `317`
- prototype: `static int(struct _GUID *__struct_ptr, struct IUnknown **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000e920`

## callees

- `0x14001fcf0`
- `0x14003e858`
- `0x140052e46`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001fddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001fe04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001fddd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001fe04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001fd55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001fd55`
- `vdsutil!VdsTraceEx` at `0x14001fd37`
- `vdsutil!VdsTraceEx` at `0x14001fdf6`
- `vdsutil!VdsTraceEx` at `0x14001fd37`
- `vdsutil!VdsTraceEx` at `0x14001fdf6`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001fd67`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001fd67`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001fd80`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001fd80`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14001fda9`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14001fda9`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14001fdce`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14001fdce`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001fd18`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001fd18`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001fe13`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001fe13`

## string_xrefs

- `0x14001fde7`: `CVdsService::GetInitiatorPortal(), 2`
- `0x14001fd08`: `CVdsService::GetInitiatorPortal()`
- `0x14001fd2b`: `CVdsService::GetInitiatorPortal(), 1`

## pseudocode

```c

```
