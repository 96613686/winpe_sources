# HandleGetExtendedError(void * const,ulong *,ulong *,char * *,char * *,char * *,ushort * *,ulong *)

- ea: `0x180094f84`
- end: `0x180095337`
- name: `?HandleGetExtendedError@@YAJQEAXPEAK1PEAPEAD22PEAPEAG1@Z`
- size: `947`
- prototype: `__int64 __fastcall(void *const, unsigned int *, unsigned int *, char **, char **, char **, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180094e30`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x18000fd04`
- `0x1800151c4`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001f968`
- `0x180020970`
- `0x180020b10`
- `0x180030120`
- `0x18003b1e0`
- `0x18003c814`
- `0x180043344`
- `0x18004e41c`
- `0x180094f84`
- `0x1800d8b90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800951a8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800951fe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180095249`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180095296`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800951a8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800951fe`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180095249`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180095296`

## string_xrefs

- `0x180094fdd`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180095054`: `hr = client.ImpersonateClient()`
- `0x1800951d4`: `hr = StringCchCopyA(*pszFileAndLine, strFileAndLine.GetLength() + 1, (LPCSTR)strFileAndLine)`
- `0x18009522e`: `hr = StringCchCopyA(*pszRequest, strRequest.GetLength() + 1, (LPCSTR)strRequest)`
- `0x180095275`: `hr = StringCchCopyA(*pszResponse, strResponse.GetLength() + 1, (LPCSTR)strResponse)`
- `0x1800952c2`: `hr = StringCchCopyW(*pwszHost, wstrHost.GetLength() + 1, (LPCWSTR)wstrHost)`

## pseudocode

```c

```
