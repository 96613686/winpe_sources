# DirectComposition::CApplicationChannel::SubmitBatch(DirectComposition::CBatch *,DirectComposition::CBatch *,bool,DirectComposition::SynchronizationObject const *)

- ea: `0x1400f5770`
- end: `0x1400f5942`
- name: `?SubmitBatch@CApplicationChannel@DirectComposition@@IEAAXPEAVCBatch@2@0_NPEBUSynchronizationObject@2@@Z`
- size: `466`
- prototype: `void(DirectComposition::CApplicationChannel *__hidden this, struct DirectComposition::CBatch *, struct DirectComposition::CBatch *, bool, const struct DirectComposition::SynchronizationObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14005764c`

## callees

- `0x14005821c`
- `0x1400f5770`
- `0x1400f5948`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f57a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f57de`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f580f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f57a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f57de`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f580f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f5842`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f58ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f58cc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f5842`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f58ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f58cc`
- `ntoskrnl!KeSetEvent` at `0x1400f5888`
- `ntoskrnl!KeSetEvent` at `0x1400f5888`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400f57ef`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400f57ef`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f57b8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f5820`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f57b8`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f5820`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400f586d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400f586d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f5836`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f58a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f58c0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f5836`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f58a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f58c0`
- `HAL!KeQueryPerformanceCounter` at `0x1400f578f`
- `HAL!KeQueryPerformanceCounter` at `0x1400f578f`

## pseudocode

```c

```
