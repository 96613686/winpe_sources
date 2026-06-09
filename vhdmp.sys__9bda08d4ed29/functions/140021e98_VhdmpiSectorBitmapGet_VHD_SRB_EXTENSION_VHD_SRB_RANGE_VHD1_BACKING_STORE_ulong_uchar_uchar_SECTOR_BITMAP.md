# VhdmpiSectorBitmapGet(_VHD_SRB_EXTENSION *,_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,ulong,uchar,uchar,_SECTOR_BITMAP * *)

- ea: `0x140021e98`
- end: `0x1400223ec`
- name: `?VhdmpiSectorBitmapGet@@YAJPEAU_VHD_SRB_EXTENSION@@PEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@KEEPEAPEAU_SECTOR_BITMAP@@@Z`
- size: `1364`
- prototype: `int(struct _VHD_SRB_EXTENSION *, struct _VHD_SRB_RANGE *, struct _VHD1_BACKING_STORE *, unsigned int, unsigned __int8, unsigned __int8, struct _SECTOR_BITMAP **)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140018480`
- `0x14001c4a0`

## callees

- `0x14001f350`
- `0x140020ac8`
- `0x140020cd0`
- `0x140021e98`
- `0x1400237b0`
- `0x140023980`
- `0x140027358`
- `0x140036284`
- `0x14003d65c`
- `0x14005e100`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021fa6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021fa6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400220a1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022206`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400220a1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140022206`

## string_xrefs

- `0x14002223f`: `VhdmpiSectorBitmapGet: a read is needed`
- `0x1400222b8`: `VhdmpiSectorBitmapGet: actually no read is needed.`

## pseudocode

```c

```
