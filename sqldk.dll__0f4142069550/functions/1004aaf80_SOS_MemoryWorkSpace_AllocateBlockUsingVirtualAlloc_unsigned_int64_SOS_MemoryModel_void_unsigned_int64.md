# SOS_MemoryWorkSpace::AllocateBlockUsingVirtualAlloc(unsigned __int64,SOS_MemoryModel,void * *,unsigned __int64 *)

- ea: `0x1004aaf80`
- end: `0x1004ab662`
- name: `?AllocateBlockUsingVirtualAlloc@SOS_MemoryWorkSpace@@AEAAPEAX_KW4SOS_MemoryModel@@PEAPEAXPEA_K@Z`
- size: `1762`
- prototype: `void *__high(unsigned __int64, enum SOS_MemoryModel, void **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x10040bc40`

## callees

- `0x1004058f0`
- `0x100413730`
- `0x100416970`
- `0x100416ad0`
- `0x100419400`
- `0x100432830`
- `0x1004360f0`
- `0x10049ef50`
- `0x1004a1440`
- `0x1004a7a20`
- `0x1004a7b10`
- `0x1004a7c90`
- `0x1004aa560`
- `0x1004aaf80`
- `0x1005b1fc0`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1004ab574`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ab5b7`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ab5e0`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ab62b`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ab574`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ab5b7`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ab5e0`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004ab62b`
- `KERNEL32!GetLastError` at `0x1004ab1cf`
- `KERNEL32!GetLastError` at `0x1004ab4be`
- `KERNEL32!GetLastError` at `0x1004ab1cf`
- `KERNEL32!GetLastError` at `0x1004ab4be`
- `KERNEL32!VirtualAlloc` at `0x1004ab1c1`
- `KERNEL32!VirtualAlloc` at `0x1004ab1c1`
- `KERNEL32!GetCurrentProcess` at `0x1004ab174`
- `KERNEL32!GetCurrentProcess` at `0x1004ab174`
- `KERNEL32!VirtualFree` at `0x1004ab4b4`
- `KERNEL32!VirtualFree` at `0x1004ab4b4`

## string_xrefs

- `0x1004ab4cb`: `Failed to release contiguous memory: %I64u bytes reserved, %I64u bytes committed at 0x%I64x; last error %d`

## pseudocode

```c

```
