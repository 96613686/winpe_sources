# CVdsService::ResetLunWrapper(_GUID &)

- ea: `0x14003c938`
- end: `0x14003ca51`
- name: `?ResetLunWrapper@CVdsService@@SAXAEAU_GUID@@@Z`
- size: `281`
- prototype: `void __fastcall(struct _GUID *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140037320`
- `0x14003bf0c`

## callees

- `0x14000bc80`
- `0x140039984`
- `0x14003c938`
- `0x140052e46`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003ca32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003ca32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c975`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c975`
- `vdsutil!VdsTraceEx` at `0x14003ca16`
- `vdsutil!VdsTraceEx` at `0x14003ca16`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c987`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c987`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c9a0`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003c9a0`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003c9c9`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003c9c9`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003ca20`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003ca20`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c958`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c958`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003ca3d`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003ca3d`

## string_xrefs

- `0x14003c948`: `CVdsService::ResetLunWrapper()`
- `0x14003ca0a`: `CVdsService::ResetLunWrapper, 1, hr=%lX`

## pseudocode

```c

```
