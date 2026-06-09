# LogWriteEntryCompletion(void *,void *,ulong,long,_LOG_WRITE_IO_CONTEXT *)

- ea: `0x1400578a0`
- end: `0x14005795f`
- name: `?LogWriteEntryCompletion@@YAJPEAX0KJPEAU_LOG_WRITE_IO_CONTEXT@@@Z`
- size: `191`
- prototype: `int(void *, void *, unsigned int, int, struct _LOG_WRITE_IO_CONTEXT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400578a0`
- `0x1400681c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140057941`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057941`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140057930`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140057930`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400578cd`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400578cd`

## pseudocode

```c

```
