# _GetPathFromBcdePath(void *,_BCDE_DEVICE const *,ushort *,ulong)

- ea: `0x1400d8774`
- end: `0x1400d8a09`
- name: `?_GetPathFromBcdePath@@YAHPEAXPEBU_BCDE_DEVICE@@PEAGK@Z`
- size: `661`
- prototype: `__int64 __fastcall(void *, const struct _BCDE_DEVICE *, unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x140023098`
- `0x1400d8a10`
- `0x1400d8ca4`

## callees

- `0x140021ca0`
- `0x14002228c`
- `0x1400235a8`
- `0x140025b00`
- `0x14005b208`
- `0x1400d257c`
- `0x1400d8774`
- `0x1400d8a10`
- `0x1400d8ca4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d89f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400d89f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d88bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d88e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d89b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d88bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d88e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d8996`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400d89b7`

## string_xrefs

- `0x1400d880e`: `pwszDevicePath`
- `0x1400d8954`: `::StringCchCopy( pwszDevicePath, cchDevicePath, pBcdeDevice->Partition.Path )`
- `0x1400d88ec`: `_GetPathFromRamdiskPath(hStore, pBcdeDevice, pwszDevicePath, cchDevicePath)`
- `0x1400d878d`: `_GetPathFromBcdePath`
- `0x1400d89e6`: `_GetPathFromBcdePath`
- `0x1400d89bd`: `_GetPathFromBootDevice(hStore, pBcdeDevice, pwszDevicePath, cchDevicePath)`

## pseudocode

```c

```
