# DirectComposition::CApplicationChannel::ReferenceHandleAndLock(uint,DirectComposition::CApplicationChannel * *)

- ea: `0x1400979b0`
- end: `0x140097b16`
- name: `?ReferenceHandleAndLock@CApplicationChannel@DirectComposition@@SAJIPEAPEAV12@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, struct DirectComposition::CApplicationChannel **)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140096364`
- `0x1400968fc`
- `0x140096c60`
- `0x140096e60`
- `0x140096ee0`
- `0x140096f80`
- `0x140097020`
- `0x1400970a0`
- `0x140097160`
- `0x140097370`
- `0x140097780`
- `0x140097820`
- `0x14021c0d0`
- `0x14021c480`

## callees

- `0x1400979b0`
- `0x1402389c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140097a04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140097a85`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140097a04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140097a85`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140097a70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140097a70`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400979c5`
- `ntoskrnl!PsGetCurrentProcessWin32Process` at `0x1400979c5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140097a15`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140097a96`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140097a15`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140097a96`
- `ntoskrnl!ExReleaseResourceLite` at `0x140097a64`
- `ntoskrnl!ExReleaseResourceLite` at `0x140097a64`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x140097a38`
- `ntoskrnl!RtlLookupElementGenericTable` at `0x140097a38`

## pseudocode

```c

```
