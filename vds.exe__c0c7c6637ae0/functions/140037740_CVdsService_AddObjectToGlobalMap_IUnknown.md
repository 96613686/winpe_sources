# CVdsService::AddObjectToGlobalMap(IUnknown *)

- ea: `0x140037740`
- end: `0x140037884`
- name: `?AddObjectToGlobalMap@CVdsService@@QEAAPEAKPEAUIUnknown@@@Z`
- size: `324`
- prototype: `char *__fastcall(CVdsService *this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140038548`

## callees

- `0x140037740`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400377f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140037853`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400377f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140037853`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400377b0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400377b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400377d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400377d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140037825`
- `vdsutil!?FindPtr@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAPEAV2@@Z` at `0x14003781b`
- `vdsutil!?FindPtr@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAPEAV2@@Z` at `0x14003781b`
- `vdsutil!?InsertUnique@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x1400377c6`
- `vdsutil!?InsertUnique@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x1400377c6`
- `vdsutil!VdsTraceEx` at `0x1400377e9`
- `vdsutil!VdsTraceEx` at `0x14003783a`
- `vdsutil!VdsTraceEx` at `0x1400377e9`
- `vdsutil!VdsTraceEx` at `0x14003783a`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037773`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037773`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037802`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003785e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037802`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003785e`

## string_xrefs

- `0x1400377dd`: `CVdsService::AddObjectToGlobalMap, 2, error = %ld`
- `0x14003782e`: `CVdsService::AddObjectToGlobalMap, 3, error = %ld`

## pseudocode

```c

```
