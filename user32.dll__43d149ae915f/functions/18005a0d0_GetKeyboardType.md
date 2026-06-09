# GetKeyboardType

- ea: `0x18005a0d0`
- end: `0x18005a19f`
- name: `GetKeyboardType`
- size: `207`
- prototype: `int __stdcall(int nTypeFlag)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x18005a0d0`
- `0x1800604ec`
- `0x180073048`

## import_xrefs

- `win32u!NtUserGetKeyboardType` at `0x18005a0f7`
- `win32u!NtUserGetKeyboardType` at `0x18005a0f7`
- `ntdll!RtlGetActiveConsoleId` at `0x18005a117`
- `ntdll!RtlGetActiveConsoleId` at `0x18005a117`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005a0eb`
- `KERNELBASE!WTSGetServiceSessionId` at `0x18005a0eb`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x18005a193`
- `ext-ms-win32-subsystem-query-l1-1-0!QueryWin32SubsystemHost` at `0x18005a193`

## pseudocode

```c

```
