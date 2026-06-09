# SOS_MemoryWorkSpace::FreePage(void *,unsigned __int64,AllocOptions,__int64 *,unsigned __int64 *)

- ea: `0x10040acc0`
- end: `0x10040ae65`
- name: `?FreePage@SOS_MemoryWorkSpace@@QEAAXPEAX_KW4AllocOptions@@PEA_JPEA_K@Z`
- size: `421`
- prototype: `void __high(void *, unsigned __int64, enum AllocOptions, __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x10040b150`
- `0x100415120`

## callees

- `0x1004058f0`
- `0x10040a7b0`
- `0x10040aaa0`
- `0x10040acc0`
- `0x10040ae70`
- `0x100413730`
- `0x1004150c0`
- `0x100419400`
- `0x1004228f0`
- `0x100432830`
- `0x1004360f0`
- `0x1004a7b10`

## import_xrefs

- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa1d4`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa212`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa26a`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa343`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa390`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa3b1`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa3fa`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa1d4`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa212`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa26a`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa343`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa390`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa3b1`
- `KERNEL32!InterlockedPushEntrySList` at `0x1004aa3fa`
- `KERNEL32!GetLastError` at `0x1004aa2ed`
- `KERNEL32!GetLastError` at `0x1004aa2ed`
- `KERNEL32!VirtualFree` at `0x1004aa2df`
- `KERNEL32!VirtualFree` at `0x1004aa2df`

## string_xrefs

- `0x1004aa2fa`: `Failed to release contiguous memory: %I64u bytes reserved, %I64u bytes committed at 0x%I64x; last error %d`

## pseudocode

```c

```
