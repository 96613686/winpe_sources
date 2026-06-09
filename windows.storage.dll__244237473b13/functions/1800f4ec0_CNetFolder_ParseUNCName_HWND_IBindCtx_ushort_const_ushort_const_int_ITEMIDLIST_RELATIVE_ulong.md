# CNetFolder::_ParseUNCName(HWND__ *,IBindCtx *,ushort const *,ushort const *,int,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x1800f4ec0`
- end: `0x1800f57e5`
- name: `?_ParseUNCName@CNetFolder@@AEAAJPEAUHWND__@@PEAUIBindCtx@@PEBG2HPEAPEAU_ITEMIDLIST_RELATIVE@@PEAK@Z`
- size: `2341`
- prototype: `__int64 __usercall@<rax>(CNetFolder *__hidden this@<rcx>, HWND@<rdx>, struct IBindCtx *@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, int, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x180257280`

## callees

- `0x180033c60`
- `0x1800551d0`
- `0x1800693a0`
- `0x1800b0560`
- `0x1800f3f90`
- `0x1800f4ec0`
- `0x1800f57ec`
- `0x180116e60`
- `0x180125320`
- `0x18012ced0`
- `0x180133f50`
- `0x1801c7b40`
- `0x180268480`
- `0x18027479c`
- `0x18027c690`
- `0x18031b63c`
- `0x1803b1f60`
- `0x18059677c`
- `0x1805977b8`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f53f4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800f53f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f539e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800f539e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f503c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f51a4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f51c9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f54c1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f503c`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f51a4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f51c9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800f54c1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f5102`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f5102`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f52e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f52fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5362`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180666953`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180666c02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f52e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f52fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5362`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180666953`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180666c02`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800f500c`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800f500c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x1800f4fe8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBackslashW` at `0x1800f4fe8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f55d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f55d6`
- `MPR!WNetUseConnectionW` at `0x1800f56d5`
- `MPR!WNetUseConnectionW` at `0x1800f56d5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathMakePrettyW` at `0x1800f5264`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathMakePrettyW` at `0x1800f5264`

## pseudocode

```c

```
