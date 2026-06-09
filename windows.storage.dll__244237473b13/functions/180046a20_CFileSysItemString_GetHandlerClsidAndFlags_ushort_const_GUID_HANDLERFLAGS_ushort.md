# CFileSysItemString::GetHandlerClsidAndFlags(ushort const *,_GUID *,HANDLERFLAGS *,ushort * *)

- ea: `0x180046a20`
- end: `0x180047188`
- name: `?GetHandlerClsidAndFlags@CFileSysItemString@@QEAAJPEBGPEAU_GUID@@PEAW4HANDLERFLAGS@@PEAPEAG@Z`
- size: `1896`
- prototype: `__int64 __usercall@<rax>(CFileSysItemString *__hidden this@<rcx>, LPCWSTR pszStr2@<rdx>, struct _GUID *@<r8>, enum HANDLERFLAGS *@<r9>, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180046670`
- `0x1800ad260`
- `0x1801170a0`

## callees

- `0x180045390`
- `0x180045520`
- `0x180045bd0`
- `0x180046a20`
- `0x180048150`
- `0x1800551d0`
- `0x1800899a4`
- `0x1800975a0`
- `0x1800ef77c`
- `0x1800efcd0`
- `0x1800fd500`
- `0x180185aa4`
- `0x180200954`
- `0x18026e3cc`
- `0x1802975e8`
- `0x180334ef8`
- `0x1803b1f60`
- `0x1803b1f84`
- `0x1803b69b9`
- `0x1803bc100`
- `0x1805626c4`
- `0x180562e98`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046bcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180046bcc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180046b96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180046b96`
- `ntdll!RtlIsPartialPlaceholder` at `0x180046b2a`
- `ntdll!RtlIsPartialPlaceholder` at `0x180046b2a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180046ab9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180046ab9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180046c55`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180046ef0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800470ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180046c55`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180046ef0`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800470ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047013`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180046c79`
- `SHCORE!__imp_SHGlobalCounterGetValue` at `0x180046c79`
- `PROPSYS!__imp_PSLookupPropertyHandlerCLSIDAndPath` at `0x18004703e`
- `PROPSYS!__imp_PSLookupPropertyHandlerCLSIDAndPath` at `0x18004703e`
- `PROPSYS!__imp_LookupHandlerInStateRepository` at `0x180046f29`
- `PROPSYS!__imp_LookupHandlerInStateRepository` at `0x180046f29`

## pseudocode

```c

```
