# DirectComposition::CApplicationChannel::SubmitBatch(DirectComposition::CBatch *,DirectComposition::CBatch *,bool,DirectComposition::SynchronizationObject const *)

- ea: `0x1400f7850`
- end: `0x1400f7a22`
- name: `?SubmitBatch@CApplicationChannel@DirectComposition@@IEAAXPEAVCBatch@2@0_NPEBUSynchronizationObject@2@@Z`
- size: `466`
- prototype: `void(DirectComposition::CApplicationChannel *__hidden this, struct DirectComposition::CBatch *, struct DirectComposition::CBatch *, bool, const struct DirectComposition::SynchronizationObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14004e88c`

## callees

- `0x14004f45c`
- `0x1400f7850`
- `0x1400f7a28`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f7887`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f78be`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f78ef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f7887`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f78be`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400f78ef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f7922`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f798c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f79ac`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f7922`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f798c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400f79ac`
- `ntoskrnl!KeSetEvent` at `0x1400f7968`
- `ntoskrnl!KeSetEvent` at `0x1400f7968`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400f78cf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400f78cf`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f7898`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f7900`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f7898`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400f7900`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400f794d`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1400f794d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f7916`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f7980`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f79a0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f7916`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f7980`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400f79a0`
- `HAL!KeQueryPerformanceCounter` at `0x1400f786f`
- `HAL!KeQueryPerformanceCounter` at `0x1400f786f`

## pseudocode

```c

```
