# GetTransactionObjects(IBindCtx *,ushort const *,ulong,IInternetProtocol * *,CTransData * *)

- ea: `0x18002441c`
- end: `0x180024a33`
- name: `?GetTransactionObjects@@YAJPEAUIBindCtx@@PEBGKPEAPEAUIInternetProtocol@@PEAPEAVCTransData@@@Z`
- size: `1559`
- prototype: `int(struct IBindCtx *, const unsigned __int16 *, unsigned int, struct IInternetProtocol **, struct CTransData **)`
- caller_count: `1`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007af20`

## callees

- `0x180008300`
- `0x1800150e0`
- `0x18002441c`
- `0x180024a3c`
- `0x180026dac`
- `0x180027228`
- `0x180028f0c`
- `0x18004ff60`
- `0x1800506a0`
- `0x1800506e4`
- `0x180054990`
- `0x18005a2f0`
- `0x18007ec94`
- `0x18009ba00`
- `0x18011ba26`
- `0x18011ba3e`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_DSA_InsertItem` at `0x18002469e`
- `iertutil!__imp_DSA_InsertItem` at `0x18002469e`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x1800244be`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x1800244be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800246b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002477e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800246b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002477e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024448`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002467b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024448`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002467b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800245eb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800245eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800244d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800244d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024847`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024847`

## string_xrefs

- `0x18002496a`: `onecoreuap\inetcore\urlmon\trans\common\ctransaction.cpp`

## pseudocode

```c

```
