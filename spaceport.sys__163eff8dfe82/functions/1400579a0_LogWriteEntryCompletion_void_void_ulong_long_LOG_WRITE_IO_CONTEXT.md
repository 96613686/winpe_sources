# LogWriteEntryCompletion(void *,void *,ulong,long,_LOG_WRITE_IO_CONTEXT *)

- ea: `0x1400579a0`
- end: `0x140057a5f`
- name: `?LogWriteEntryCompletion@@YAJPEAX0KJPEAU_LOG_WRITE_IO_CONTEXT@@@Z`
- size: `191`
- prototype: `int(void *, void *, unsigned int, int, struct _LOG_WRITE_IO_CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400579a0`
- `0x140068300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140057a41`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057a41`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140057a30`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140057a30`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400579cd`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400579cd`

## pseudocode

```c

```
