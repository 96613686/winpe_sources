# CVdsService::RemoveRawDisk(ushort *,ulong)

- ea: `0x14003c340`
- end: `0x14003c41c`
- name: `?RemoveRawDisk@CVdsService@@SAHPEAGK@Z`
- size: `220`
- prototype: `__int64 __fastcall(wchar_t *String1, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x14003c150`
- `0x14004fd50`

## callees

- `0x14003bf0c`
- `0x14003c340`
- `0x14003c514`
- `0x14003ca88`
- `0x14004dbac`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14003c3a5`
- `msvcrt!_wcsicmp` at `0x14003c3a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c3fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003c3fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c36c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003c36c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c35e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003c35e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c409`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003c409`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003c3b4`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003c3b4`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003c37f`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003c37f`

## string_xrefs

- `0x14003c34d`: `CVdsService::RemoveRawDisk()(2)`

## pseudocode

```c

```
