# CEcsPath::ClearReadOnly(void *)

- ea: `0x180061990`
- end: `0x180061b0f`
- name: `?ClearReadOnly@CEcsPath@@SAJPEAX@Z`
- size: `383`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800593c8`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x180007e10`
- `0x180008080`
- `0x180011314`
- `0x180061990`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180061a91`
- `ntdll!NtQueryInformationFile` at `0x180061a91`
- `ntdll!NtSetInformationFile` at `0x180061ad8`
- `ntdll!NtSetInformationFile` at `0x180061ad8`

## string_xrefs

- `0x180061a11`: `CEcsPath::ClearReadOnly`

## pseudocode

```c

```
