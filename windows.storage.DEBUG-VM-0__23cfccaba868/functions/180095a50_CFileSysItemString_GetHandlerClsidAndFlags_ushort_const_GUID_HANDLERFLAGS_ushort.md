# CFileSysItemString::GetHandlerClsidAndFlags(ushort const *,_GUID *,HANDLERFLAGS *,ushort * *)

- ea: `0x180095a50`
- end: `0x180096179`
- name: `?GetHandlerClsidAndFlags@CFileSysItemString@@QEAAJPEBGPEAU_GUID@@PEAW4HANDLERFLAGS@@PEAPEAG@Z`
- size: `1833`
- prototype: `__int64 __usercall@<rax>(CFileSysItemString *__hidden this@<rcx>, LPCWSTR pszStr2@<rdx>, struct _GUID *@<r8>, enum HANDLERFLAGS *@<r9>, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008c9e0`
- `0x1800956b0`
- `0x18010ae40`

## callees

- `0x180015ee0`
- `0x180093d60`
- `0x180093ef0`
- `0x180094c70`
- `0x180095a50`
- `0x1800970c0`
- `0x1800a00b0`
- `0x1800b9680`
- `0x1800b9b90`
- `0x1800dd190`
- `0x18012c990`
- `0x180181898`
- `0x1801de540`
- `0x18026004c`
- `0x18028a5a4`
- `0x1803226f4`
- `0x1803a4cb0`
- `0x1803a4cd4`
- `0x1803a96d9`
- `0x1803aee20`
- `0x18054a5b0`
- `0x18054ad54`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180095bea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180095bea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180095bba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180095bba`
- `ntdll!RtlIsPartialPlaceholder` at `0x180095b54`
- `ntdll!RtlIsPartialPlaceholder` at `0x180095b54`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180095ae9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180095ae9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180095c6d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180095eff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800960e5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180095c6d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180095eff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800960e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096016`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180095c8b`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180095c8b`
- `PROPSYS!__imp_PSLookupPropertyHandlerCLSIDAndPath` at `0x18009603b`
- `PROPSYS!__imp_PSLookupPropertyHandlerCLSIDAndPath` at `0x18009603b`
- `PROPSYS!__imp_LookupHandlerInStateRepository` at `0x180095f32`
- `PROPSYS!__imp_LookupHandlerInStateRepository` at `0x180095f32`

## pseudocode

```c

```
