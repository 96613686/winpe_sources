# CVdsService::AddObjectToMap(IUnknown *,IUnknown *)

- ea: `0x140008410`
- end: `0x140008577`
- name: `?AddObjectToMap@CVdsService@@QEAAHPEAUIUnknown@@0@Z`
- size: `359`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct IUnknown *, struct IUnknown *)`
- caller_count: `6`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140001980`
- `0x140004d80`
- `0x140005630`
- `0x14001bb50`
- `0x14003c668`
- `0x14003d900`

## callees

- `0x140008410`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400084ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008559`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400084ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008559`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000848b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000848b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008527`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x1400084a1`
- `vdsutil!?Find@CRtlMap@@QEAAHAEAVCRtlEntry@@PEAV2@@Z` at `0x1400084a1`
- `vdsutil!?Insert@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x1400084c0`
- `vdsutil!?Insert@CRtlMap@@QEAAHAEAVCRtlEntry@@0@Z` at `0x1400084c0`
- `vdsutil!VdsTraceEx` at `0x1400084e3`
- `vdsutil!VdsTraceEx` at `0x14000854f`
- `vdsutil!VdsTraceEx` at `0x1400084e3`
- `vdsutil!VdsTraceEx` at `0x14000854f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000844b`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000844b`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400084f9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140008565`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x1400084f9`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140008565`

## string_xrefs

- `0x14000843a`: `CVdsService::AddObjectToMap()`

## pseudocode

```c

```
