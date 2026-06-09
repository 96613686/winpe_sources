# CEnumDevicesRequest::GetResponse(ulong *,ushort * * *,ushort * * *,ulong *,ulong *)

- ea: `0x1800cf25c`
- end: `0x1800cf4cd`
- name: `?GetResponse@CEnumDevicesRequest@@QEAAJPEAKPEAPEAPEAG100@Z`
- size: `625`
- prototype: `__int64 __fastcall(CEnumDevicesRequest *__hidden this, unsigned int *, unsigned __int16 ***, unsigned __int16 ***, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009939c`

## callees

- `0x18000c050`
- `0x180037e48`
- `0x1800cdd94`
- `0x1800cf25c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cf45d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cf46b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cf45d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800cf46b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cf317`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cf338`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cf317`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800cf338`

## string_xrefs

- `0x1800cf44e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x1800cf432`: `hr = SafeCopyMemory(pCurName, dwNamesSize - (pCurName - reinterpret_cast<PBYTE>(apszNames)), (PCWSTR)pItem->pszDeviceName, dwTempLen)`
- `0x1800cf423`: `hr = SafeCopyMemory(pCurFName, dwFriendlyNamesSize - (pCurName - reinterpret_cast<PBYTE>(apszFriendlyNames)), (PCWSTR) pItem->pszFriendlyName, dwTempLen)`

## pseudocode

```c

```
