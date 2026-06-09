# GetSslDWordFromRegistry

- ea: `0x180047ef8`
- end: `0x180047fa0`
- name: `GetSslDWordFromRegistry`
- size: `168`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180087038`
- `0x1800876f8`

## callees

- `0x180047ef8`
- `0x1800597b0`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180047f67`
- `ntdll!NtQueryValueKey` at `0x180047f67`
- `ntdll!RtlInitUnicodeString` at `0x180047f3c`
- `ntdll!RtlInitUnicodeString` at `0x180047f3c`

## pseudocode

```c

```
