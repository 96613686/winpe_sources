# SOS_MemoryWorkSpace::DeCommitBlock(void *,unsigned __int64,SOS_TopLevelBlockDescriptor *,ushort,ushort,int,unsigned __int64 *,unsigned __int64 *)

- ea: `0x100432830`
- end: `0x100432acb`
- name: `?DeCommitBlock@SOS_MemoryWorkSpace@@CAXPEAX_KPEAVSOS_TopLevelBlockDescriptor@@GGHPEA_K3@Z`
- size: `667`
- prototype: `void __fastcall(void *, unsigned __int64, struct SOS_TopLevelBlockDescriptor *, unsigned __int16, unsigned __int16, int, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x10040aaa0`
- `0x10040acc0`
- `0x100413ec0`
- `0x1004aab70`
- `0x1004aaf80`

## callees

- `0x100403070`
- `0x100404bf2`
- `0x1004058f0`
- `0x100411fb0`
- `0x100413730`
- `0x100413810`
- `0x100419400`
- `0x100432830`
- `0x1004360f0`
- `0x1004a21c0`

## import_xrefs

- `KERNEL32!MapUserPhysicalPages` at `0x1004aaaa4`
- `KERNEL32!MapUserPhysicalPages` at `0x1004aaaa4`
- `KERNEL32!VirtualUnlock` at `0x1004aa9a4`
- `KERNEL32!VirtualUnlock` at `0x1004aa9a4`
- `KERNEL32!GetLastError` at `0x1004aa9b0`
- `KERNEL32!GetLastError` at `0x1004aa9b0`
- `KERNEL32!VirtualAlloc` at `0x1004aa98f`
- `KERNEL32!VirtualAlloc` at `0x1004aa98f`
- `KERNEL32!VirtualFree` at `0x100432a02`
- `KERNEL32!VirtualFree` at `0x100432a02`

## string_xrefs

- `0x1004aa9bd`: `Failed to decommit contiguous memory: %I64u bytes at 0x%I64x; last error %d`

## pseudocode

```c

```
