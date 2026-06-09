# DirectComposition::CApplicationChannel::SubmitBatch(DirectComposition::CBatch *,DirectComposition::CBatch *,bool,DirectComposition::SynchronizationObject const *)

- ea: `0x1400fa8a4`
- end: `0x1400faa76`
- name: `?SubmitBatch@CApplicationChannel@DirectComposition@@IEAAXPEAVCBatch@2@0_NPEBUSynchronizationObject@2@@Z`
- size: `466`
- prototype: `void(DirectComposition::CApplicationChannel *__hidden this, struct DirectComposition::CBatch *, struct DirectComposition::CBatch *, bool, const struct DirectComposition::SynchronizationObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140088e3c`

## callees

- `0x140089a0c`
- `0x1400fa8a4`
- `0x1400faa7c`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fa8db`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fa912`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fa943`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fa8db`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fa912`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400fa943`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fa976`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fa9e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400faa00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fa976`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400fa9e0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400faa00`
- `ntoskrnl!KeSetEvent` at `0x1400fa9bc`
- `ntoskrnl!KeSetEvent` at `0x1400fa9bc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fa923`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400fa923`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fa8ec`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fa954`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fa8ec`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400fa954`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400fa9a1`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400fa9a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fa96a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fa9d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fa9f4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fa96a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fa9d4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400fa9f4`
- `HAL!KeQueryPerformanceCounter` at `0x1400fa8c3`
- `HAL!KeQueryPerformanceCounter` at `0x1400fa8c3`

## pseudocode

```c

```
