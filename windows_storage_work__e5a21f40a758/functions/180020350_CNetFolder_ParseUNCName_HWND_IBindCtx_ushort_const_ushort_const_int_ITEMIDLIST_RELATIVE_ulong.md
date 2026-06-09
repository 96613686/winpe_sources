# CNetFolder::_ParseUNCName(HWND__ *,IBindCtx *,ushort const *,ushort const *,int,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x180020350`
- end: `0x180020c6c`
- name: `?_ParseUNCName@CNetFolder@@AEAAJPEAUHWND__@@PEAUIBindCtx@@PEBG2HPEAPEAU_ITEMIDLIST_RELATIVE@@PEAK@Z`
- size: `2332`
- prototype: `__int64 __usercall@<rax>(CNetFolder *__hidden this@<rcx>, HWND@<rdx>, struct IBindCtx *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, int, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180246360`

## callees

- `0x18000ee84`
- `0x18001f410`
- `0x180020350`
- `0x180020c74`
- `0x18004e540`
- `0x1800a3080`
- `0x1800d7650`
- `0x18012c990`
- `0x18015adb0`
- `0x18016cd40`
- `0x1801b0400`
- `0x180256a7c`
- `0x18026491c`
- `0x180267364`
- `0x180267588`
- `0x18030a420`
- `0x1803a4cb0`
- `0x18057b57c`
- `0x18057c530`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002083e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002083e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800207ee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800207ee`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800204c0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180020619`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180020638`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180020905`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800204c0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180020619`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180020638`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x180020905`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020580`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020580`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002074c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002075a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18063e771`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002074c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002075a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800207b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020c03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18063e771`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x180020496`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x180020496`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180020478`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x180020478`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020a14`
- `MPR!WNetUseConnectionW` at `0x180020b0d`
- `MPR!WNetUseConnectionW` at `0x180020b0d`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathMakePrettyW` at `0x1800206cd`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathMakePrettyW` at `0x1800206cd`

## pseudocode

```c

```
