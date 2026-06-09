# PfsGetNTFSFileIndexNumber

- ea: `0x180085dcc`
- end: `0x180085ef5`
- name: `PfsGetNTFSFileIndexNumber`
- size: `297`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x18008aac8`

## callees

- `0x180085dcc`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180085e83`
- `ntdll!NtCreateFile` at `0x180085e83`
- `ntdll!NtQueryInformationFile` at `0x180085eb3`
- `ntdll!NtQueryInformationFile` at `0x180085eb3`
- `ntdll!RtlInitUnicodeString` at `0x180085e0c`
- `ntdll!RtlInitUnicodeString` at `0x180085e0c`
- `ntdll!RtlNtStatusToDosError` at `0x180085e8f`
- `ntdll!RtlNtStatusToDosError` at `0x180085e8f`
- `ntdll!NtClose` at `0x180085edc`
- `ntdll!NtClose` at `0x180085edc`

## pseudocode

```c

```
