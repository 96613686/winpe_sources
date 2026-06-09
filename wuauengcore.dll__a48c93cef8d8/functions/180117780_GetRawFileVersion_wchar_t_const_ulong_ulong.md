# GetRawFileVersion(wchar_t const *,ulong *,ulong *)

- ea: `0x180117780`
- end: `0x180117abe`
- name: `?GetRawFileVersion@@YAJPEB_WPEAK1@Z`
- size: `830`
- prototype: `__int64 __fastcall(LPCWSTR lpwstrFilename, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1801176a4`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x180113ae8`
- `0x180113b9c`
- `0x180117780`
- `0x180117ac4`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011783a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011783a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117a7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117a89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117a7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180117a89`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180117884`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180117884`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011782b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011782b`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180117a4d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180117a4d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801178d1`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x1801178d1`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1801178fb`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFileEx` at `0x1801178fb`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1801179cf`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1801179cf`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1801179ac`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x1801179ac`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180117960`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180117960`

## pseudocode

```c

```
