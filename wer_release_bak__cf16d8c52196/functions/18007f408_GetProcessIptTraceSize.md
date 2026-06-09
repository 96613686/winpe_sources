# GetProcessIptTraceSize

- ea: `0x18007f408`
- end: `0x18007f52a`
- name: `GetProcessIptTraceSize`
- size: `290`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002054c`
- `0x180027bc8`

## callees

- `0x18002babc`
- `0x180050db0`
- `0x18007f3d4`
- `0x18007f408`

## import_xrefs

- `ntdll!RtlReleasePrivilege` at `0x18007f4e4`
- `ntdll!RtlReleasePrivilege` at `0x18007f4e4`
- `ntdll!NtDeviceIoControlFile` at `0x18007f4ca`
- `ntdll!NtDeviceIoControlFile` at `0x18007f4ca`
- `ntdll!NtClose` at `0x18007f4d6`
- `ntdll!NtClose` at `0x18007f4d6`

## pseudocode

```c

```
