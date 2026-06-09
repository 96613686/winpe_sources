# CFspFileSystemOperations::Exists(ushort const *,int *)

- ea: `0x1801121e8`
- end: `0x1801123da`
- name: `?Exists@CFspFileSystemOperations@@SAJPEBGPEAH@Z`
- size: `498`
- prototype: `__int64 __fastcall(PCWSTR SourceString, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18010e5b8`

## callees

- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x1801121e8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1801122db`
- `ntdll!RtlInitUnicodeString` at `0x1801122db`
- `ntdll!NtCreateFile` at `0x18011234e`
- `ntdll!NtCreateFile` at `0x18011234e`
- `ntdll!NtClose` at `0x18011235e`
- `ntdll!NtClose` at `0x18011235e`

## pseudocode

```c

```
