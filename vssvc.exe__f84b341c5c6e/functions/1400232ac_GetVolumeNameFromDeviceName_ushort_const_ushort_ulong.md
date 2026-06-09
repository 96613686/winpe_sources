# GetVolumeNameFromDeviceName(ushort const *,ushort *,ulong)

- ea: `0x1400232ac`
- end: `0x1400235a0`
- name: `?GetVolumeNameFromDeviceName@@YAHPEBGPEAGK@Z`
- size: `756`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: `reparse_path`

## callers

- `0x1400229e4`
- `0x140058f70`
- `0x1400d763c`

## callees

- `0x140010170`
- `0x1400232ac`
- `0x14003ade4`
- `0x14003b0c0`
- `0x14005b208`
- `0x140091560`
- `0x1400921dc`
- `0x1400d257c`
- `0x1400d7ebc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002356d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002356d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400234f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002350b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400234f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002350b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400234e4`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1400234e4`

## string_xrefs

- `0x1400234cd`: `::StringCchCat( wszPath, ARRAYSIZE(wszPath), L"\\" )`
- `0x140023511`: `::GetVolumeNameForVolumeMountPoint( wszPath, pwszVolumeName, cchVolumeName )`
- `0x140023430`: `DevicePathToWin32Path( (WCHAR*)pwszDeviceName, ARRAY_COUNT_PARAM(wszPath))`

## pseudocode

```c

```
