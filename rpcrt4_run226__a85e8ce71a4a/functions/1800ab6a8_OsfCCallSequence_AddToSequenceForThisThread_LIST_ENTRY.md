# OsfCCallSequence::AddToSequenceForThisThread(_LIST_ENTRY *)

- ea: `0x1800ab6a8`
- end: `0x1800ab752`
- name: `?AddToSequenceForThisThread@OsfCCallSequence@@SAJPEAU_LIST_ENTRY@@@Z`
- size: `170`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800ab758`

## callees

- `0x180021e70`
- `0x1800280b0`
- `0x1800ab6a8`

## import_xrefs

- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800ab6e4`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800ab6e4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ab73a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800ab73a`
- `ntdll!RtlEnterCriticalSection` at `0x1800ab70b`
- `ntdll!RtlEnterCriticalSection` at `0x1800ab70b`

## pseudocode

```c

```
