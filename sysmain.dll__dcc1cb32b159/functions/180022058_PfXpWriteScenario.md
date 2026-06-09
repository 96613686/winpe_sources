# PfXpWriteScenario

- ea: `0x180022058`
- end: `0x180022369`
- name: `PfXpWriteScenario`
- size: `785`
- prototype: `__int64 __fastcall(__int64, __int64, WCHAR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180033740`

## callees

- `0x1800211f4`
- `0x180022058`
- `0x180022370`
- `0x1800231b0`
- `0x180023244`
- `0x180023480`
- `0x18003aa6c`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x1800222fc`
- `ntdll!NtSetSystemInformation` at `0x1800222fc`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002221e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002221e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180022249`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180022249`
- `ntdll!RtlNtStatusToDosError` at `0x18002219a`
- `ntdll!RtlNtStatusToDosError` at `0x18002230c`
- `ntdll!RtlNtStatusToDosError` at `0x18002219a`
- `ntdll!RtlNtStatusToDosError` at `0x18002230c`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180022108`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180022108`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800220f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800220f2`

## pseudocode

```c

```
