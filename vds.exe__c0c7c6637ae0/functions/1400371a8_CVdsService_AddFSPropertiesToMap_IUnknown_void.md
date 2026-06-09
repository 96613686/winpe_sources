# CVdsService::AddFSPropertiesToMap(IUnknown *,void *)

- ea: `0x1400371a8`
- end: `0x140037319`
- name: `?AddFSPropertiesToMap@CVdsService@@QEAAHPEAUIUnknown@@PEAX@Z`
- size: `369`
- prototype: `__int64 __fastcall(CVdsService *__hidden this, struct IUnknown *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1400037a0`

## callees

- `0x1400371a8`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003728c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400372bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003728c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400372bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140037246`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140037246`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400372a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400372a9`
- `vdsutil!?FindPtr@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAPEAV2@@Z` at `0x14003729f`
- `vdsutil!?FindPtr@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAPEAV2@@Z` at `0x14003729f`
- `vdsutil!?InsertUnique@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x14003725f`
- `vdsutil!?InsertUnique@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x14003725f`
- `vdsutil!VdsTraceEx` at `0x140037282`
- `vdsutil!VdsTraceEx` at `0x1400372e7`
- `vdsutil!VdsTraceEx` at `0x140037282`
- `vdsutil!VdsTraceEx` at `0x1400372e7`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400371e3`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400371e3`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400372c6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400372f2`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400372c6`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400372f2`

## string_xrefs

- `0x1400372db`: `CVdsService::AddFSPropertiesToMap, 1, pObject=%p, pFSProp=%p`
- `0x140037273`: `CVdsService::AddFSPropertiesToMap, 2, error = %ld`
- `0x1400372af`: `CVdsService::AddFSPropertiesToMap, 3, error = %ld`

## pseudocode

```c

```
