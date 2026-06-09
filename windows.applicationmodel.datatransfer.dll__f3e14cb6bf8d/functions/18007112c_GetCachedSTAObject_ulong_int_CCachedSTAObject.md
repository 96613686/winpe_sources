# _GetCachedSTAObject(ulong,int *,CCachedSTAObject * *)

- ea: `0x18007112c`
- end: `0x180071230`
- name: `?_GetCachedSTAObject@@YAJKPEAHPEAPEAVCCachedSTAObject@@@Z`
- size: `260`
- prototype: `__int64 __fastcall(DWORD dwTlsIndex, int *, struct CCachedSTAObject **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180071238`

## callees

- `0x180002ea0`
- `0x180005504`
- `0x18007112c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800711ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800711ca`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180071142`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180071142`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800711db`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x1800711db`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18007119e`
- `api-ms-win-core-com-private-l1-1-0!CoRegisterInitializeSpy` at `0x18007119e`

## pseudocode

```c

```
