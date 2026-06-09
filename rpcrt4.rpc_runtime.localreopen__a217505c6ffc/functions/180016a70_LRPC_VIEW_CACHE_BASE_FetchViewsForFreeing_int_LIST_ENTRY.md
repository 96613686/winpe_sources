# LRPC_VIEW_CACHE_BASE::FetchViewsForFreeing(int,_LIST_ENTRY *)

- ea: `0x180016a70`
- end: `0x180016d36`
- name: `?FetchViewsForFreeing@LRPC_VIEW_CACHE_BASE@@QEAAXHPEAU_LIST_ENTRY@@@Z`
- size: `710`
- prototype: `void __fastcall(LRPC_VIEW_CACHE_BASE *__hidden this, int, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800169ec`

## callees

- `0x1800162a8`
- `0x180016a70`
- `0x180017ba0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180016b28`
- `ntdll!RtlLeaveCriticalSection` at `0x180016b9b`
- `ntdll!RtlLeaveCriticalSection` at `0x180016b28`
- `ntdll!RtlLeaveCriticalSection` at `0x180016b9b`
- `ntdll!RtlEnterCriticalSection` at `0x180016ae8`
- `ntdll!RtlEnterCriticalSection` at `0x180016b60`
- `ntdll!RtlEnterCriticalSection` at `0x180016ae8`
- `ntdll!RtlEnterCriticalSection` at `0x180016b60`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180016baf`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedFlushSList` at `0x180016baf`

## pseudocode

```c

```
