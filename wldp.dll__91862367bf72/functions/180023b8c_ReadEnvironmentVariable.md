# ReadEnvironmentVariable

- ea: `0x180023b8c`
- end: `0x180023c5d`
- name: `ReadEnvironmentVariable`
- size: `209`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180023cd0`

## callees

- `0x180021ec0`
- `0x180023b8c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023c08`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023c08`
- `ntdll!RtlInitUnicodeString` at `0x180023bc2`
- `ntdll!RtlInitUnicodeString` at `0x180023bc2`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180023be1`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180023c36`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180023be1`
- `ntdll!NtQuerySystemEnvironmentValueEx` at `0x180023c36`

## pseudocode

```c

```
