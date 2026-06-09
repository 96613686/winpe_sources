# CVdsService::RemoveLunIdFromMap(ushort *)

- ea: `0x14003bf0c`
- end: `0x14003c07e`
- name: `?RemoveLunIdFromMap@CVdsService@@CAJPEAG@Z`
- size: `370`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14003c194`
- `0x14003c340`

## callees

- `0x14003995c`
- `0x14003bdec`
- `0x14003bf0c`
- `0x14003c938`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14003bf9b`
- `msvcrt!_wcsicmp` at `0x14003bf9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c05b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c05b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003bf50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003bf50`
- `vdsutil!VdsTraceEx` at `0x14003c03a`
- `vdsutil!VdsTraceEx` at `0x14003c03a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003bf42`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003bf42`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c066`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c066`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003bfa9`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003bfa9`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003bf62`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003bf62`

## string_xrefs

- `0x14003bf34`: `CVdsService::RemoveLunIdFromMap()`

## pseudocode

```c

```
