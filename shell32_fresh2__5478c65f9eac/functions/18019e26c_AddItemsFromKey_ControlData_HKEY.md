# _AddItemsFromKey(ControlData *,HKEY__ *)

- ea: `0x18019e26c`
- end: `0x18019e530`
- name: `?_AddItemsFromKey@@YAXPEAUControlData@@PEAUHKEY__@@@Z`
- size: `708`
- prototype: `void __fastcall(struct ControlData *, HKEY hKey)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180050530`

## callees

- `0x180050818`
- `0x180065190`
- `0x18019e26c`
- `0x180249490`
- `0x18024a53c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18019e35f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18019e35f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18019e48a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18019e48a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019e4fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18019e4fc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18019e4e3`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18019e4e3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019e2de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019e2de`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18019e3bc`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18019e3bc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18019e391`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18019e391`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18019e3de`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18019e3de`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18019e44c`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18019e44c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18019e416`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18019e416`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18019e3f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18019e435`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18019e3f5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18019e435`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18019e32f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18019e32f`

## pseudocode

```c

```
