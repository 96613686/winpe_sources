# BiGetPhysicalDiskNumber

- ea: `0x180068c2c`
- end: `0x180068d51`
- name: `BiGetPhysicalDiskNumber`
- size: `293`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180068d58`
- `0x18006bca8`

## callees

- `0x180068c2c`
- `0x180068e10`

## import_xrefs

- `ntdll!ZwClose` at `0x180068d2d`
- `ntdll!ZwClose` at `0x180068d2d`
- `ntdll!ZwOpenFile` at `0x180068cc6`
- `ntdll!ZwOpenFile` at `0x180068cc6`
- `ntdll!RtlFreeHeap` at `0x180068d18`
- `ntdll!RtlFreeHeap` at `0x180068d18`
- `ntdll!RtlInitUnicodeString` at `0x180068c6f`
- `ntdll!RtlInitUnicodeString` at `0x180068c6f`

## pseudocode

```c

```
