# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180050964`
- end: `0x180050a19`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18004f98c`
- `0x180051c78`
- `0x18005218c`

## callees

- `0x180050964`
- `0x1800cb010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800509b6`
- `KERNEL32!LoadLibraryExW` at `0x1800509b6`
- `KERNEL32!GetProcAddress` at `0x18005099e`
- `KERNEL32!GetProcAddress` at `0x1800509cb`
- `KERNEL32!GetProcAddress` at `0x18005099e`
- `KERNEL32!GetProcAddress` at `0x1800509cb`
- `KERNEL32!GetModuleHandleW` at `0x180050989`
- `KERNEL32!GetModuleHandleW` at `0x180050989`
- `KERNEL32!GetLastError` at `0x180050a07`
- `KERNEL32!GetLastError` at `0x180050a07`

## string_xrefs

- `0x180050982`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180050994`: `RegDeleteKeyExW`
- `0x1800509af`: `advapi32.dll`
- `0x1800509c1`: `RegDeleteKeyW`

## pseudocode

```c

```
