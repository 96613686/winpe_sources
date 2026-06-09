# CVdsRawDiskLun::CleanDiskThreadEntry(void *)

- ea: `0x14004d8f0`
- end: `0x14004d984`
- name: `?CleanDiskThreadEntry@CVdsRawDiskLun@@SAKPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(CVdsRawDiskLun **Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000f600`
- `0x14004d8f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004d94a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14004d94a`
- `vdsutil!VdsHeapFree` at `0x14004d958`
- `vdsutil!VdsHeapFree` at `0x14004d958`
- `vdsutil!VdsTraceEx` at `0x14004d935`
- `vdsutil!VdsTraceEx` at `0x14004d935`
- `vdsutil!AcquireRundownProtection` at `0x14004d91c`
- `vdsutil!AcquireRundownProtection` at `0x14004d91c`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004d90e`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14004d90e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004d971`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14004d971`
- `vdsutil!ReleaseRundownProtection` at `0x14004d965`
- `vdsutil!ReleaseRundownProtection` at `0x14004d965`

## string_xrefs

- `0x14004d8fd`: `CVdsRawDiskLun::CleanDiskThreadEntry()`
- `0x14004d928`: `CVdsRawDiskLun::CleanDiskThreadEntry exiting due to shutdown`

## pseudocode

```c

```
