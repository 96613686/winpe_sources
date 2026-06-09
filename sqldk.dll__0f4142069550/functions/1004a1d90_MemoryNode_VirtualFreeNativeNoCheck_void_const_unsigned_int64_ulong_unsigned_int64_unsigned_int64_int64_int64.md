# MemoryNode::VirtualFreeNativeNoCheck(void * const,unsigned __int64,ulong,unsigned __int64,unsigned __int64,__int64 *,__int64 *)

- ea: `0x1004a1d90`
- end: `0x1004a1f59`
- name: `?VirtualFreeNativeNoCheck@MemoryNode@@AEAA?AW4SOS_RESULT@@QEAX_KK_K2PEA_J3@Z`
- size: `457`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10049e250`
- `0x1004a1990`

## callees

- `0x100413730`
- `0x100419400`
- `0x1004360f0`
- `0x1004a1d90`

## import_xrefs

- `KERNEL32!VirtualUnlock` at `0x1004a1e14`
- `KERNEL32!VirtualUnlock` at `0x1004a1e14`
- `KERNEL32!GetLastError` at `0x1004a1e32`
- `KERNEL32!GetLastError` at `0x1004a1e32`
- `KERNEL32!VirtualAlloc` at `0x1004a1dff`
- `KERNEL32!VirtualAlloc` at `0x1004a1dff`
- `KERNEL32!VirtualFree` at `0x1004a1e28`
- `KERNEL32!VirtualFree` at `0x1004a1e28`

## string_xrefs

- `0x1004a1e49`: `Failed to decommit contiguous memory: %I64u bytes at 0x%I64x; last error %d`
- `0x1004a1e9e`: `Failed to release contiguous memory: %I64u bytes reserved, %I64u bytes committed at 0x%I64x; last error %d`

## pseudocode

```c

```
