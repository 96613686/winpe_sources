# GetSslStringFromRegistry

- ea: `0x180087d00`
- end: `0x180087de4`
- name: `GetSslStringFromRegistry`
- size: `228`
- prototype: `__int64 __fastcall(HANDLE KeyHandle, PCWSTR SourceString, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180087038`
- `0x1800873b0`
- `0x1800876f8`
- `0x180087a30`

## callees

- `0x1800597b0`
- `0x18005a160`
- `0x18005f160`
- `0x180087d00`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x180087d83`
- `ntdll!NtQueryValueKey` at `0x180087d83`
- `ntdll!RtlInitUnicodeString` at `0x180087d58`
- `ntdll!RtlInitUnicodeString` at `0x180087d58`

## pseudocode

```c

```
