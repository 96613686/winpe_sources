# _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)

- ea: `0x18007d830`
- end: `0x18007d974`
- name: `?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z`
- size: `324`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, struct CCachedSTAObject **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007866c`
- `0x18007db90`

## callees

- `0x18002b1e0`
- `0x180077ba0`
- `0x18007c180`
- `0x18007d830`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007d904`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007d904`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007d89e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18007d89e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18007d910`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18007d910`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18007d8dc`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18007d8dc`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007d874`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18007d874`

## pseudocode

```c

```
