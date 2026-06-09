# GetProcessIptTraceSize

- ea: `0x180082ecc`
- end: `0x180083001`
- name: `GetProcessIptTraceSize`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180021024`
- `0x180028c4c`

## callees

- `0x18002d4d4`
- `0x180053300`
- `0x180082e94`
- `0x180082ecc`

## import_xrefs

- `ntdll!RtlReleasePrivilege` at `0x180082fb4`
- `ntdll!RtlReleasePrivilege` at `0x180082fb4`
- `ntdll!NtDeviceIoControlFile` at `0x180082f8e`
- `ntdll!NtDeviceIoControlFile` at `0x180082f8e`
- `ntdll!NtClose` at `0x180082fa0`
- `ntdll!NtClose` at `0x180082fa0`

## pseudocode

```c

```
