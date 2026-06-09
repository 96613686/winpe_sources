# DirectComposition::CApplicationChannel::ReferenceHandleAndLock(uint,DirectComposition::CApplicationChannel * *)

- ea: `0x14005fc70`
- end: `0x14005fdd6`
- name: `?ReferenceHandleAndLock@CApplicationChannel@DirectComposition@@SAJIPEAPEAV12@@Z`
- size: `358`
- prototype: `__int64 __fastcall(unsigned int, struct DirectComposition::CApplicationChannel **)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14005e624`
- `0x14005ebbc`
- `0x14005ef20`
- `0x14005f120`
- `0x14005f1a0`
- `0x14005f240`
- `0x14005f2e0`
- `0x14005f360`
- `0x14005f420`
- `0x14005f630`
- `0x14005fa40`
- `0x14005fae0`
- `0x14021b820`
- `0x14021bbd0`

## callees

- `0x14005fc70`
- `0x140238240`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14005fcc4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005fd45`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005fcc4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14005fd45`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fd30`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005fd30`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14005fc85`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x14005fc85`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fcd5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fd56`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fcd5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14005fd56`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fd24`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005fd24`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x14005fcf8`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x14005fcf8`

## pseudocode

```c

```
