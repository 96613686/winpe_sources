# DirectComposition::CApplicationChannel::ReferenceHandleAndLock(uint,DirectComposition::CApplicationChannel * *)

- ea: `0x1400bceb0`
- end: `0x1400bd016`
- name: `?ReferenceHandleAndLock@CApplicationChannel@DirectComposition@@SAJIPEAPEAV12@@Z`
- size: `358`
- prototype: `__int64 __fastcall(unsigned int, struct DirectComposition::CApplicationChannel **)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400bb864`
- `0x1400bbdfc`
- `0x1400bc160`
- `0x1400bc360`
- `0x1400bc3e0`
- `0x1400bc480`
- `0x1400bc520`
- `0x1400bc5a0`
- `0x1400bc660`
- `0x1400bc870`
- `0x1400bcc80`
- `0x1400bcd20`
- `0x14021c040`
- `0x14021c3f0`

## callees

- `0x1400bceb0`
- `0x140238bf0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcf04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcf85`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcf04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400bcf85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcf70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400bcf70`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400bcec5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400bcec5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400bcf15`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400bcf96`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400bcf15`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400bcf96`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400bcf64`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400bcf64`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x1400bcf38`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x1400bcf38`

## pseudocode

```c

```
