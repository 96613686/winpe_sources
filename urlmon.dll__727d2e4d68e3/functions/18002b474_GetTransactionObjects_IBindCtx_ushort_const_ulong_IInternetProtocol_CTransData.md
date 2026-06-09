# GetTransactionObjects(IBindCtx *,ushort const *,ulong,IInternetProtocol * *,CTransData * *)

- ea: `0x18002b474`
- end: `0x18002babb`
- name: `?GetTransactionObjects@@YAJPEAUIBindCtx@@PEBGKPEAPEAUIInternetProtocol@@PEAPEAVCTransData@@@Z`
- size: `1607`
- prototype: `__int64 __fastcall(struct IBindCtx *, CBinding *, unsigned int, struct IInternetProtocol **, struct CTransData **)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x180080c50`

## callees

- `0x180008b2c`
- `0x18001db50`
- `0x18002b474`
- `0x18002bac4`
- `0x18002debc`
- `0x18002e300`
- `0x18002e3ac`
- `0x18002f348`
- `0x18002fee0`
- `0x180030e40`
- `0x18004bbf0`
- `0x18005aee4`
- `0x18005fa60`
- `0x180083bec`
- `0x1800a2600`
- `0x1801285e6`
- `0x1801285fe`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_DSA_InsertItem` at `0x18002b714`
- `iertutil!__imp_DSA_InsertItem` at `0x18002b714`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18002b51c`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x18002b51c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b734`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b800`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b734`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b800`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b4a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b6eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b4a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002b6eb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002b655`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002b655`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b537`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b537`

## string_xrefs

- `0x18002b9f2`: `onecoreuap\inetcore\urlmon\trans\common\ctransaction.cpp`

## pseudocode

```c

```
