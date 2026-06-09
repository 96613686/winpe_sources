# CVdsService::GetDiskId(ushort *,_GUID *)

- ea: `0x14001b958`
- end: `0x14001bb12`
- name: `?GetDiskId@CVdsService@@SAJPEAGPEAU_GUID@@@Z`
- size: `442`
- prototype: `__int64 __fastcall(wchar_t *String1, struct _GUID *)`
- caller_count: `5`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x140001980`
- `0x140023f58`
- `0x140027890`
- `0x140038a70`
- `0x14003db30`

## callees

- `0x140003710`
- `0x140004360`
- `0x140012c48`
- `0x140013298`
- `0x14001b958`
- `0x14001f220`
- `0x140038618`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `vdsutil!VdsTraceEx` at `0x14001babf`
- `vdsutil!VdsTraceEx` at `0x14001babf`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b9fe`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001b9fe`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001ba17`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14001ba17`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14001ba44`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14001ba44`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14001bad2`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14001bad2`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001b97f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14001b97f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001bafe`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14001bafe`

## string_xrefs

- `0x14001b96f`: `CVdsService::GetDiskId()`
- `0x14001bab3`: `CVdsService::GetDiskId: unexpected error from provider: %X`

## pseudocode

```c

```
