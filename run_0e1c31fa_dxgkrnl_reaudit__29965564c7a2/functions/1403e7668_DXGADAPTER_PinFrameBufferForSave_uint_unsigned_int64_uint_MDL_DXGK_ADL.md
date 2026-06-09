# DXGADAPTER::PinFrameBufferForSave(uint,unsigned __int64,uint,_MDL * *,_DXGK_ADL * *)

- ea: `0x1403e7668`
- end: `0x1403e7aed`
- name: `?PinFrameBufferForSave@DXGADAPTER@@QEAAJI_KIPEAPEAU_MDL@@PEAPEAU_DXGK_ADL@@@Z`
- size: `1157`
- prototype: `__int64 __fastcall(DXGADAPTER *__hidden this, unsigned int, unsigned __int64, unsigned int, struct _MDL **, struct _DXGK_ADL **)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140035470`
- `0x1400354b0`

## callees

- `0x14001b9c0`
- `0x14001d214`
- `0x14003d8d0`
- `0x14003e610`
- `0x14003e898`
- `0x14003e9c0`
- `0x140044270`
- `0x1403e7668`

## import_xrefs

- `ntoskrnl!MmMapViewInSystemSpace` at `0x1403e77b6`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1403e77b6`
- `ntoskrnl!IoAllocateMdl` at `0x1403e780b`
- `ntoskrnl!IoAllocateMdl` at `0x1403e780b`
- `ntoskrnl!MmProbeAndLockPages` at `0x1403e7882`
- `ntoskrnl!MmProbeAndLockPages` at `0x1403e7882`
- `ntoskrnl!MmUnlockPages` at `0x1403e7a98`
- `ntoskrnl!MmUnlockPages` at `0x1403e7a98`
- `ntoskrnl!IoFreeMdl` at `0x1403e7aac`
- `ntoskrnl!IoFreeMdl` at `0x1403e7aac`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1403e7ac2`
- `ntoskrnl!MmUnmapViewInSystemSpace` at `0x1403e7ac2`
- `watchdog!WdLogSingleEntry0` at `0x1403e7827`
- `watchdog!WdLogSingleEntry0` at `0x1403e79ea`
- `watchdog!WdLogSingleEntry0` at `0x1403e7827`
- `watchdog!WdLogSingleEntry0` at `0x1403e79ea`
- `watchdog!WdLogSingleEntry1` at `0x1403e769a`
- `watchdog!WdLogSingleEntry1` at `0x1403e76fd`
- `watchdog!WdLogSingleEntry1` at `0x1403e7764`
- `watchdog!WdLogSingleEntry1` at `0x1403e77d9`
- `watchdog!WdLogSingleEntry1` at `0x1403e78d9`
- `watchdog!WdLogSingleEntry1` at `0x1403e797c`
- `watchdog!WdLogSingleEntry1` at `0x1403e769a`
- `watchdog!WdLogSingleEntry1` at `0x1403e76fd`
- `watchdog!WdLogSingleEntry1` at `0x1403e7764`
- `watchdog!WdLogSingleEntry1` at `0x1403e77d9`
- `watchdog!WdLogSingleEntry1` at `0x1403e78d9`
- `watchdog!WdLogSingleEntry1` at `0x1403e797c`

## string_xrefs

- `0x1403e7736`: `PinFrameBufferForSave CommitSize (%I64u) is not a multiple of PAGE_SIZE`
- `0x1403e777a`: `Frame buffer save area already pinned for PhysicalAdapterIndex %u. PinFrameBufferForSave cannot be called again without first calling Unpin.`

## pseudocode

```c

```
