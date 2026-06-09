# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180092fc8`
- end: `0x18009307d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18008a14c`
- `0x18009828c`
- `0x18009876c`

## callees

- `0x180092fc8`
- `0x18028b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009301a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18009301a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180092fed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180092fed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180093002`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009302f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180093002`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009302f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009306b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009306b`

## string_xrefs

- `0x180092fe6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180092ff8`: `RegDeleteKeyExW`
- `0x180093013`: `advapi32.dll`
- `0x180093025`: `RegDeleteKeyW`

## pseudocode

```c

```
