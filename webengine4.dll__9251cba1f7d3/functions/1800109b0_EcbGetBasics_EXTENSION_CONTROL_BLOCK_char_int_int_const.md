# EcbGetBasics(_EXTENSION_CONTROL_BLOCK *,char *,int,int * const)

- ea: `0x1800109b0`
- end: `0x180010cda`
- name: `?EcbGetBasics@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEADHQEAH@Z`
- size: `810`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, char *, int, int *const)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001e8c8`

## callees

- `0x1800109b0`
- `0x180010ce0`
- `0x18004d030`
- `0x18004d350`
- `0x1800653ba`
- `0x1800653ec`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180010b16`
- `KERNEL32!GetLastError` at `0x180010b16`
- `KERNEL32!lstrlenA` at `0x180010aa4`
- `KERNEL32!lstrlenA` at `0x180010ab2`
- `KERNEL32!lstrlenA` at `0x180010ac2`
- `KERNEL32!lstrlenA` at `0x180010ad1`
- `KERNEL32!lstrlenA` at `0x180010ade`
- `KERNEL32!lstrlenA` at `0x180010aa4`
- `KERNEL32!lstrlenA` at `0x180010ab2`
- `KERNEL32!lstrlenA` at `0x180010ac2`
- `KERNEL32!lstrlenA` at `0x180010ad1`
- `KERNEL32!lstrlenA` at `0x180010ade`
- `ucrtbase_clr0400!strncmp` at `0x180010b72`
- `ucrtbase_clr0400!strncmp` at `0x180010b72`

## string_xrefs

- `0x180010a16`: `APPL_PHYSICAL_PATH`
- `0x180010b47`: `PATH_INFO`
- `0x180010a5c`: `APPL_MD_PATH`

## pseudocode

```c

```
