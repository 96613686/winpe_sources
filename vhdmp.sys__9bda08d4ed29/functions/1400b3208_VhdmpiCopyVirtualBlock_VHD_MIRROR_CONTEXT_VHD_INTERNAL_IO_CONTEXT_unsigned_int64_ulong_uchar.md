# VhdmpiCopyVirtualBlock(_VHD_MIRROR_CONTEXT *,_VHD_INTERNAL_IO_CONTEXT *,unsigned __int64,ulong,uchar)

- ea: `0x1400b3208`
- end: `0x1400b36c2`
- name: `?VhdmpiCopyVirtualBlock@@YAJPEAU_VHD_MIRROR_CONTEXT@@PEAU_VHD_INTERNAL_IO_CONTEXT@@_KKE@Z`
- size: `1210`
- prototype: `int(struct _VHD_MIRROR_CONTEXT *, struct _VHD_INTERNAL_IO_CONTEXT *, unsigned __int64, unsigned int, unsigned __int8)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400b4470`
- `0x1400b5e0c`

## callees

- `0x1400010d0`
- `0x1400014d8`
- `0x14001dfd4`
- `0x140023980`
- `0x14004da58`
- `0x14004e2c8`
- `0x14005dbb0`
- `0x14005dc30`
- `0x1400b3208`
- `0x1400b6fb4`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x1400b32bc`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400b3461`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400b363a`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400b32bc`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400b3461`
- `ntoskrnl!KeReleaseSemaphore` at `0x1400b363a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b34b8`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b34b8`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b32f1`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b34d8`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b32f1`
- `ntoskrnl!EtwActivityIdControl` at `0x1400b34d8`

## pseudocode

```c

```
