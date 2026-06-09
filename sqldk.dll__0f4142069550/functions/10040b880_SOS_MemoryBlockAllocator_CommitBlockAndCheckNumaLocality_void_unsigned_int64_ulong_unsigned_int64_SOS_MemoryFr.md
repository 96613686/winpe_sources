# SOS_MemoryBlockAllocator::CommitBlockAndCheckNumaLocality(void *,unsigned __int64,ulong,unsigned __int64,SOS_MemoryFreeBlock *,SOS_ParentBlockDescriptor *,SOS_MemoryBlockAllocator::CheckNuma,ushort,bool,unsigned __int64 *,__int64 *)

- ea: `0x10040b880`
- end: `0x10040baff`
- name: `?CommitBlockAndCheckNumaLocality@SOS_MemoryBlockAllocator@@AEAA?AW4CommitResult@1@PEAX_KK1PEAVSOS_MemoryFreeBlock@@PEAVSOS_ParentBlockDescriptor@@W4CheckNuma@1@G_NPEA_KPEA_J@Z`
- size: `639`
- prototype: `enum SOS_MemoryBlockAllocator::CommitResult __high(void *, unsigned __int64, unsigned int, unsigned __int64, struct SOS_MemoryFreeBlock *, struct SOS_ParentBlockDescriptor *, enum SOS_MemoryBlockAllocator::CheckNuma, unsigned __int16, bool, unsigned __int64 *, __int64 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x10040b4b0`
- `0x100498b90`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x1004058f0`
- `0x10040b880`
- `0x100411fb0`
- `0x100413730`
- `0x100413810`
- `0x100413cc0`
- `0x100413dc0`
- `0x100413e30`
- `0x100413ec0`
- `0x100419400`
- `0x100426a00`
- `0x1004325b0`
- `0x1004360f0`
- `0x1004a2090`
- `0x1004a21c0`
- `0x1004a6ca0`
- `0x1004a6de0`

## import_xrefs

- `KERNEL32!VirtualProtect` at `0x10049afc3`
- `KERNEL32!VirtualProtect` at `0x10049b085`
- `KERNEL32!VirtualProtect` at `0x10049afc3`
- `KERNEL32!VirtualProtect` at `0x10049b085`
- `KERNEL32!InterlockedPushEntrySList` at `0x10043358e`
- `KERNEL32!InterlockedPushEntrySList` at `0x10043358e`
- `KERNEL32!MapUserPhysicalPages` at `0x10049ac50`
- `KERNEL32!MapUserPhysicalPages` at `0x10049ac50`
- `KERNEL32!MapUserPhysicalPagesScatter` at `0x10049aa6e`
- `KERNEL32!MapUserPhysicalPagesScatter` at `0x10049aa6e`
- `KERNEL32!VirtualUnlock` at `0x10049a709`
- `KERNEL32!VirtualUnlock` at `0x10049a709`
- `KERNEL32!GetLastError` at `0x10049a715`
- `KERNEL32!GetLastError` at `0x10049a715`
- `KERNEL32!VirtualAlloc` at `0x10049a6f4`
- `KERNEL32!VirtualAlloc` at `0x10049a6f4`
- `KERNEL32!VirtualFree` at `0x10042872f`
- `KERNEL32!VirtualFree` at `0x10042872f`

## string_xrefs

- `0x10049a736`: `Failed to decommit contiguous memory: %I64u bytes at 0x%I64x; last error %d`

## pseudocode

```c

```
