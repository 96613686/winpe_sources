# IsUnderWow64(void)

- ea: `0x18004a55c`
- end: `0x18004a5bf`
- name: `?IsUnderWow64@@YAHXZ`
- size: `99`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180040fa0`

## callees

- `0x18004a55c`
- `0x18004d350`
- `0x180065b60`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x18004a591`
- `KERNEL32!GetCurrentProcess` at `0x18004a591`
- `KERNEL32!GetModuleHandleW` at `0x18004a56e`
- `KERNEL32!GetModuleHandleW` at `0x18004a56e`
- `KERNEL32!GetProcAddress` at `0x18004a583`
- `KERNEL32!GetProcAddress` at `0x18004a583`

## string_xrefs

- `0x18004a567`: `kernel32.dll`

## pseudocode

```c

```
