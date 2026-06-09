# CSPPMetadataManager::ReadMetadataFromFile(ushort *,uchar * *,ulong *)

- ea: `0x140084c54`
- end: `0x140084ed9`
- name: `?ReadMetadataFromFile@CSPPMetadataManager@@CAJPEAGPEAPEAEPEAK@Z`
- size: `645`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned __int8 **, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1400834c8`
- `0x140084a08`

## callees

- `0x140006ca8`
- `0x14000bb24`
- `0x14000cbcc`
- `0x140014260`
- `0x140084c54`

## import_xrefs

- `KERNEL32!ReadFile` at `0x140084e1a`
- `KERNEL32!ReadFile` at `0x140084e1a`
- `KERNEL32!GetFileSizeEx` at `0x140084d7d`
- `KERNEL32!GetFileSizeEx` at `0x140084d7d`
- `KERNEL32!CreateFileW` at `0x140084d49`
- `KERNEL32!CreateFileW` at `0x140084d49`
- `KERNEL32!CloseHandle` at `0x140084e5d`
- `KERNEL32!CloseHandle` at `0x140084e5d`
- `KERNEL32!GetLastError` at `0x140084d58`
- `KERNEL32!GetLastError` at `0x140084d87`
- `KERNEL32!GetLastError` at `0x140084e24`
- `KERNEL32!GetLastError` at `0x140084d58`
- `KERNEL32!GetLastError` at `0x140084d87`
- `KERNEL32!GetLastError` at `0x140084e24`
- `ole32!CoTaskMemFree` at `0x140084e4d`
- `ole32!CoTaskMemFree` at `0x140084e4d`

## string_xrefs

- `0x140084cab`: `base\stor\blb\engine\service\sppmetadatamanager.cpp`

## pseudocode

```c

```
