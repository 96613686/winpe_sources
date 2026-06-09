# SettingsCopier::GetRegKeyValue(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong *,ATL::CHeapPtr<uchar,ATL::CCRTAllocator> &,ulong *)

- ea: `0x180387630`
- end: `0x18038790c`
- name: `?GetRegKeyValue@SettingsCopier@@CAJPEAUHKEY__@@PEBGKPEAGKPEAKAEAV?$CHeapPtr@EVCCRTAllocator@ATL@@@ATL@@3@Z`
- size: `732`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, DWORD cchValueName, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config`

## callers

- `0x1803870ac`

## callees

- `0x180387060`
- `0x180387630`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18038768e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180387828`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180387895`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803878cc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18038768e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180387828`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180387895`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1803878cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1803876a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1803876a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18038786d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18038786d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803876af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803876af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803876f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803877bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387878`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803876f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387733`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803877bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387815`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180387878`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180387856`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180387856`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180387724`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180387724`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18038777e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180387806`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18038777e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180387806`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038773d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803877c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038781f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387862`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038773d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803877c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18038781f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180387862`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1803876e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1803876e5`

## string_xrefs

- `0x18038784f`: `SymbolicLinkValue`

## pseudocode

```c

```
