# OsfCCallSequence::AddToSequenceForThisThread(_LIST_ENTRY *)

- ea: `0x1800af0d4`
- end: `0x1800af191`
- name: `?AddToSequenceForThisThread@OsfCCallSequence@@SAJPEAU_LIST_ENTRY@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800af198`

## callees

- `0x180023020`
- `0x1800292c0`
- `0x1800af0d4`

## import_xrefs

- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800af110`
- `ntdll!RtlInitializeCriticalSectionAndSpinCount` at `0x1800af110`
- `ntdll!RtlLeaveCriticalSection` at `0x1800af172`
- `ntdll!RtlLeaveCriticalSection` at `0x1800af172`
- `ntdll!RtlEnterCriticalSection` at `0x1800af13d`
- `ntdll!RtlEnterCriticalSection` at `0x1800af13d`

## pseudocode

```c

```
