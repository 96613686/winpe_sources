# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800528c8`
- end: `0x18005299c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180051850`
- `0x180053d3c`
- `0x180054298`

## callees

- `0x1800528c8`
- `0x1800d1010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180052926`
- `KERNEL32!LoadLibraryExW` at `0x180052926`
- `KERNEL32!GetProcAddress` at `0x180052908`
- `KERNEL32!GetProcAddress` at `0x180052941`
- `KERNEL32!GetProcAddress` at `0x180052908`
- `KERNEL32!GetProcAddress` at `0x180052941`
- `KERNEL32!GetModuleHandleW` at `0x1800528ed`
- `KERNEL32!GetModuleHandleW` at `0x1800528ed`
- `KERNEL32!GetLastError` at `0x180052983`
- `KERNEL32!GetLastError` at `0x180052983`

## string_xrefs

- `0x1800528e6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800528fe`: `RegDeleteKeyExW`
- `0x18005291f`: `advapi32.dll`
- `0x180052937`: `RegDeleteKeyW`

## pseudocode

```c

```
