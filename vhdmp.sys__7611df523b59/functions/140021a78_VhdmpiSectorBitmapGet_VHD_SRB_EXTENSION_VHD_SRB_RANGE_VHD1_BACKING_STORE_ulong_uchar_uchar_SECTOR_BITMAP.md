# VhdmpiSectorBitmapGet(_VHD_SRB_EXTENSION *,_VHD_SRB_RANGE *,_VHD1_BACKING_STORE *,ulong,uchar,uchar,_SECTOR_BITMAP * *)

- ea: `0x140021a78`
- end: `0x140021fcc`
- name: `?VhdmpiSectorBitmapGet@@YAJPEAU_VHD_SRB_EXTENSION@@PEAU_VHD_SRB_RANGE@@PEAU_VHD1_BACKING_STORE@@KEEPEAPEAU_SECTOR_BITMAP@@@Z`
- size: `1364`
- prototype: `int(struct _VHD_SRB_EXTENSION *, struct _VHD_SRB_RANGE *, struct _VHD1_BACKING_STORE *, unsigned int, unsigned __int8, unsigned __int8, struct _SECTOR_BITMAP **)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x140017fe0`
- `0x14001c080`

## callees

- `0x14001ef30`
- `0x1400206a8`
- `0x1400208b0`
- `0x140021a78`
- `0x140023390`
- `0x140023560`
- `0x140026e34`
- `0x140035e94`
- `0x14003d26c`
- `0x14005dd00`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021b86`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140021b86`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021c81`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021de6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021c81`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140021de6`

## string_xrefs

- `0x140021e98`: `VhdmpiSectorBitmapGet: actually no read is needed.`
- `0x140021e1f`: `VhdmpiSectorBitmapGet: a read is needed`

## pseudocode

```c

```
