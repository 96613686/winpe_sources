# CVdsService::GetLunIdFromMap(ushort *,_GUID *)

- ea: `0x140022d0c`
- end: `0x140022e77`
- name: `?GetLunIdFromMap@CVdsService@@SAJPEAGPEAU_GUID@@@Z`
- size: `363`
- prototype: `__int64 __fastcall(wchar_t *String1, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140004d80`

## callees

- `0x140022d0c`
- `0x14003995c`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140022d9d`
- `msvcrt!_wcsicmp` at `0x140022d9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140022e51`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140022e51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140022d5d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140022d5d`
- `vdsutil!VdsTraceEx` at `0x140022e43`
- `vdsutil!VdsTraceEx` at `0x140022e43`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140022d48`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140022d48`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140022e5c`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140022e5c`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x140022dab`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x140022dab`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x140022d6f`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x140022d6f`

## string_xrefs

- `0x140022d3a`: `CVdsService::GetLunIdFromMap()`

## pseudocode

```c

```
