# WFDSConMgr::RPC::CClientContext::OnAsyncCall(_RPC_ASYNC_STATE *,ulong *,uchar * *)

- ea: `0x18000a208`
- end: `0x18000a43a`
- name: `?OnAsyncCall@CClientContext@RPC@WFDSConMgr@@QEAA_NPEAU_RPC_ASYNC_STATE@@PEAKPEAPEAE@Z`
- size: `562`
- prototype: `bool __fastcall(WFDSConMgr::RPC::CClientContext *__hidden this, struct _RPC_ASYNC_STATE *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180007004`

## callees

- `0x1800059c0`
- `0x180006740`
- `0x1800072fc`
- `0x180009c80`
- `0x180009ff4`
- `0x18000a208`
- `0x18000a6f4`
- `0x18000ab00`
- `0x18000ab0c`
- `0x18005c888`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a35c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a41c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a35c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3bb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a41c`

## string_xrefs

- `0x18000a260`: `Tried to set async call parameters multiple times before completion`

## pseudocode

```c

```
