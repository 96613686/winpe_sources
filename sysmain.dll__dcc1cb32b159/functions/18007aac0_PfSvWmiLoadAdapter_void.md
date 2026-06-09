# PfSvWmiLoadAdapter(void)

- ea: `0x18007aac0`
- end: `0x18007abd3`
- name: `?PfSvWmiLoadAdapter@@YAJXZ`
- size: `275`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18007af90`
- `0x18007b0f0`
- `0x18007b130`

## callees

- `0x18007aa84`
- `0x18007aac0`
- `0x18007b190`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18007ab71`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18007ab71`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007ab8a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007abbe`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007ab8a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18007abbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007aae5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ab0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ab2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ab44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ab5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ab0d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ab2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ab44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007ab5c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007ab93`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007ab93`

## string_xrefs

- `0x18007ab03`: `Adapter_RegisterDLL`
- `0x18007ab22`: `Adapter_UnRegisterDLL`
- `0x18007ab3a`: `Adapter_DllCanUnloadNow`
- `0x18007ab52`: `Adapter_DllGetClassObject`

## pseudocode

```c

```
