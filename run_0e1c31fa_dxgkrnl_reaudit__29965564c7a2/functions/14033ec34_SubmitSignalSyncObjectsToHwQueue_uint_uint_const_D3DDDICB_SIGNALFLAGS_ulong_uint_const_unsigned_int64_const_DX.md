# SubmitSignalSyncObjectsToHwQueue(uint,uint const *,_D3DDDICB_SIGNALFLAGS,ulong,uint const *,unsigned __int64 const *,DXGPROCESS *,bool,bool)

- ea: `0x14033ec34`
- end: `0x1403406c9`
- name: `?SubmitSignalSyncObjectsToHwQueue@@YAJIPEBIU_D3DDDICB_SIGNALFLAGS@@K0PEB_KPEAVDXGPROCESS@@_N4@Z`
- size: `6805`
- prototype: `__int64 __usercall@<rax>(unsigned int@<ecx>, const unsigned int *@<rdx>, struct _D3DDDICB_SIGNALFLAGS@<r8d>, unsigned int@<r9d>, const unsigned int *, const unsigned __int64 *, struct DXGPROCESS *, bool, bool)`
- caller_count: `3`
- callee_count: `38`
- tags: ``

## callers

- `0x140340828`
- `0x140345090`
- `0x1403def20`

## callees

- `0x140012540`
- `0x140014950`
- `0x140015940`
- `0x140015b30`
- `0x140015f30`
- `0x140018054`
- `0x14001ac50`
- `0x14001b9c0`
- `0x14001c5c0`
- `0x14001cd10`
- `0x14001d1a0`
- `0x14001d274`
- `0x14001f2f0`
- `0x14001f630`
- `0x14001fa40`
- `0x1400203d0`
- `0x140021cf0`
- `0x14002dbc0`
- `0x14002dd50`
- `0x14002def0`
- `0x14002ee60`
- `0x140030a30`
- `0x140033da4`
- `0x14003be8c`
- `0x1400427bc`
- `0x140047990`
- `0x140048a5c`
- `0x1400674c4`
- `0x1400a0bd0`
- `0x1400a0d00`
- `0x1400a1000`
- `0x1401a3f84`
- `0x1403344b8`
- `0x1403345d0`
- `0x14033ebec`
- `0x14033ec34`
- `0x1403406d0`
- `0x140340750`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033efa9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033fc0f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033efa9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14033fc0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f50f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f548`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f5ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f6a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f722`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f73e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f75a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f776`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f792`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f91d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f940`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f95c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f978`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f994`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fa36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fa75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033faac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fb6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fcb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033ff88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340010`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403400bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340100`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340131`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340223`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340267`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340298`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403402fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034049a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403404ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403405f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034066f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340682`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340695`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f50f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f548`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f5ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f6a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f722`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f73e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f75a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f776`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f792`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f91d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f940`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f95c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f978`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f994`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fa36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fa75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033faac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fb6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fcb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fec7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033ff88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340010`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403400bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340100`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340131`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340223`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340267`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340298`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403402fb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034049a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403404ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403405f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034066f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340682`
- `ntoskrnl!ExFreePoolWithTag` at `0x140340695`
- `ntoskrnl!ExAllocatePool2` at `0x14034047c`
- `ntoskrnl!ExAllocatePool2` at `0x14034047c`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14033ef9d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14033fc03`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14033ef9d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14033fc03`
- `watchdog!WdLogSingleEntry4` at `0x14033fc4d`
- `watchdog!WdLogSingleEntry4` at `0x14033fd32`
- `watchdog!WdLogSingleEntry4` at `0x1403401be`
- `watchdog!WdLogSingleEntry4` at `0x14033fc4d`
- `watchdog!WdLogSingleEntry4` at `0x14033fd32`
- `watchdog!WdLogSingleEntry4` at `0x1403401be`
- `watchdog!WdLogSingleEntry2` at `0x14034060b`
- `watchdog!WdLogSingleEntry2` at `0x14034060b`
- `watchdog!WdLogSingleEntry3` at `0x140340040`
- `watchdog!WdLogSingleEntry3` at `0x14034032c`
- `watchdog!WdLogSingleEntry3` at `0x14034052f`
- `watchdog!WdLogSingleEntry3` at `0x140340040`
- `watchdog!WdLogSingleEntry3` at `0x14034032c`
- `watchdog!WdLogSingleEntry3` at `0x14034052f`
- `watchdog!WdLogSingleEntry0` at `0x14033f825`
- `watchdog!WdLogSingleEntry0` at `0x14033fb9c`
- `watchdog!WdLogSingleEntry0` at `0x14033ff9b`
- `watchdog!WdLogSingleEntry0` at `0x1403404c3`
- `watchdog!WdLogSingleEntry0` at `0x140340582`
- `watchdog!WdLogSingleEntry0` at `0x1403405a6`
- `watchdog!WdLogSingleEntry0` at `0x14033f825`
- `watchdog!WdLogSingleEntry0` at `0x14033fb9c`
- `watchdog!WdLogSingleEntry0` at `0x14033ff9b`
- `watchdog!WdLogSingleEntry0` at `0x1403404c3`
- `watchdog!WdLogSingleEntry0` at `0x140340582`
- `watchdog!WdLogSingleEntry0` at `0x1403405a6`
- `watchdog!WdLogSingleEntry1` at `0x14033f31d`
- `watchdog!WdLogSingleEntry1` at `0x14033f49d`
- `watchdog!WdLogSingleEntry1` at `0x14033f8d4`
- `watchdog!WdLogSingleEntry1` at `0x14033fe68`
- `watchdog!WdLogSingleEntry1` at `0x14033f31d`
- `watchdog!WdLogSingleEntry1` at `0x14033f49d`
- `watchdog!WdLogSingleEntry1` at `0x14033f8d4`
- `watchdog!WdLogSingleEntry1` at `0x14033fe68`

## string_xrefs

- `0x140340654`: `SignalSynchronizationObjectFromGpu on device 0x%p attempts to use a sync object opened on a different device 0x%p.`
- `0x14033fe9d`: `0x%I64x object is opened with NoSignal flag and thus cannot be signaled.`
- `0x14034008c`: `0x%I64x failed, failed to create a sync object on logical adapter 0x%I64x returning 0x%I64x`
- `0x14033f4dc`: `0x%I64x encountered exception when copying monitored fence value array.`

## pseudocode

```c

```
