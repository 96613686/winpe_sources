# CApplicationPreLaunchNotifications::ConvertWin32PathToNtPath(ushort const *,ulong,ushort *)

- ea: `0x1800b13c8`
- end: `0x1800b15cc`
- name: `?ConvertWin32PathToNtPath@CApplicationPreLaunchNotifications@@AEAAJPEBGKPEAG@Z`
- size: `516`
- prototype: `int(CApplicationPreLaunchNotifications *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x1800c929c`

## callees

- `0x180058a44`
- `0x1800b13c8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800b13fd`
- `ntdll!RtlInitUnicodeString` at `0x1800b13fd`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800b1410`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800b1410`
- `ntdll!NtCreateFile` at `0x1800b149f`
- `ntdll!NtCreateFile` at `0x1800b149f`
- `ntdll!NtQueryObject` at `0x1800b14d2`
- `ntdll!NtQueryObject` at `0x1800b14d2`
- `ntdll!RtlFreeHeap` at `0x1800b1500`
- `ntdll!RtlFreeHeap` at `0x1800b1581`
- `ntdll!RtlFreeHeap` at `0x1800b1500`
- `ntdll!RtlFreeHeap` at `0x1800b1581`
- `ntdll!RtlAllocateHeap` at `0x1800b151d`
- `ntdll!RtlAllocateHeap` at `0x1800b151d`
- `ntdll!RtlUpcaseUnicodeString` at `0x1800b154a`
- `ntdll!RtlUpcaseUnicodeString` at `0x1800b154a`
- `ntdll!NtClose` at `0x1800b1597`
- `ntdll!NtClose` at `0x1800b1597`
- `ntdll!RtlFreeUnicodeString` at `0x1800b15a8`
- `ntdll!RtlFreeUnicodeString` at `0x1800b15a8`

## pseudocode

```c

```
