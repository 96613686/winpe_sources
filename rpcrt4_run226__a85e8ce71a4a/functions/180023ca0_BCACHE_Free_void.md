# BCACHE::Free(void *)

- ea: `0x180023ca0`
- end: `0x180023f7a`
- name: `?Free@BCACHE@@QEAAXPEAX@Z`
- size: `730`
- prototype: `void __fastcall(BCACHE *__hidden this, void *)`
- caller_count: `27`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001050`
- `0x180002b7c`
- `0x180018d9c`
- `0x18001a4f0`
- `0x18001c140`
- `0x18001dd40`
- `0x18001f070`
- `0x180021fc0`
- `0x1800229b0`
- `0x180025130`
- `0x180025280`
- `0x180025630`
- `0x180025c90`
- `0x18002acd0`
- `0x1800313e8`
- `0x180037ed0`
- `0x1800381b0`
- `0x180038c40`
- `0x18004b4f0`
- `0x18004b800`
- `0x180074450`
- `0x180078f40`
- `0x1800791a0`
- `0x180081170`
- `0x180087e30`
- `0x1800cdaa0`
- `0x1800d1040`

## callees

- `0x180021e18`
- `0x180022870`
- `0x180023ca0`
- `0x18008c120`
- `0x1800ca140`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlGetCurrentProcessorNumber` at `0x180023d2d`
- `ntdll!RtlGetCurrentProcessorNumber` at `0x180023d2d`
- `ntdll!DbgPrint` at `0x180023f45`
- `ntdll!DbgPrint` at `0x180023f5b`
- `ntdll!DbgPrint` at `0x180023f45`
- `ntdll!DbgPrint` at `0x180023f5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023e76`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180023d58`
- `api-ms-win-core-interlocked-l1-1-0!QueryDepthSList` at `0x180023d58`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180023d75`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180023d75`

## string_xrefs

- `0x180023f3e`: `RPC: BCache corruption detected at 0x%p\n`
- `0x180023f54`: `RPC: BCache corruption detected at 0x%p\n`

## pseudocode

```c

```
