# LRPC_VIEW_CACHE_BASE::InsertView(LRPC_CACHED_VIEW_BASE *,ulong)

- ea: `0x180017ba0`
- end: `0x180017c51`
- name: `?InsertView@LRPC_VIEW_CACHE_BASE@@IEAAXPEAVLRPC_CACHED_VIEW_BASE@@K@Z`
- size: `177`
- prototype: `void(LRPC_VIEW_CACHE_BASE *__hidden this, struct LRPC_CACHED_VIEW_BASE *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180016a70`
- `0x180016f98`
- `0x180017a94`
- `0x1800713ec`

## callees

- `0x180017ba0`
- `0x180017c58`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180017c43`
- `ntdll!RtlLeaveCriticalSection` at `0x180017c43`
- `ntdll!RtlEnterCriticalSection` at `0x180017bf2`
- `ntdll!RtlEnterCriticalSection` at `0x180017bf2`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180017c1c`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180017c1c`

## pseudocode

```c

```
