# BuildEnvironmentPath(void * *,ushort const *,ushort const *)

- ea: `0x140008870`
- end: `0x140008a1a`
- name: `?BuildEnvironmentPath@@YAHPEAPEAXPEBG1@Z`
- size: `426`
- prototype: `__int64 __fastcall(PWSTR *Environment, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x140007e30`

## callees

- `0x140008870`
- `0x1400198e0`
- `0x14001a200`
- `0x14009cc54`

## import_xrefs

- `ntdll!RtlSetEnvironmentVariable` at `0x1400089de`
- `ntdll!RtlSetEnvironmentVariable` at `0x1400089de`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1400088e4`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x14000894c`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x1400088e4`
- `ntdll!RtlQueryEnvironmentVariable_U` at `0x14000894c`
- `ntdll!RtlInitUnicodeString` at `0x1400088d1`
- `ntdll!RtlInitUnicodeString` at `0x1400089c9`
- `ntdll!RtlInitUnicodeString` at `0x1400088d1`
- `ntdll!RtlInitUnicodeString` at `0x1400089c9`

## pseudocode

```c

```
