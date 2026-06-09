# LogCoreWriteDataRecord(_LOG_HANDLE *,void *,void *,ulong,void *,ulong,void *,ulong,_SL_LSN *)

- ea: `0x140003fc0`
- end: `0x140004243`
- name: `?LogCoreWriteDataRecord@@YAJPEAU_LOG_HANDLE@@PEAX1K1K1KPEAT_SL_LSN@@@Z`
- size: `643`
- prototype: `__int64 __usercall@<rax>(struct _LOG_HANDLE *@<rcx>, void *@<rdx>, void *@<r8>, unsigned int@<r9d>, void *Src, size_t Size, void *, unsigned int, union _SL_LSN *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003df0`

## callees

- `0x140003fc0`
- `0x140004250`
- `0x140024f30`
- `0x140026bb0`
- `0x140057160`
- `0x140068300`
- `0x140068600`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000414b`
- `ntoskrnl!ExAllocatePool2` at `0x14000414b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004233`
- `ntoskrnl!ExFreePoolWithTag` at `0x140004233`

## pseudocode

```c

```
