# LRPC_VIEW_CACHE_BASE::InsertView(LRPC_CACHED_VIEW_BASE *,ulong)

- ea: `0x18004baec`
- end: `0x18004bb8a`
- name: `?InsertView@LRPC_VIEW_CACHE_BASE@@IEAAXPEAVLRPC_CACHED_VIEW_BASE@@K@Z`
- size: `158`
- prototype: `void(LRPC_VIEW_CACHE_BASE *__hidden this, struct LRPC_CACHED_VIEW_BASE *, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18004b9e8`
- `0x18004ce6c`
- `0x18004d254`
- `0x180072538`

## callees

- `0x18004baec`
- `0x18004bb90`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18004bb82`
- `ntdll!RtlLeaveCriticalSection` at `0x18004bb82`
- `ntdll!RtlEnterCriticalSection` at `0x18004bb3d`
- `ntdll!RtlEnterCriticalSection` at `0x18004bb3d`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18004bb61`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x18004bb61`

## pseudocode

```c

```
