# CFSFolder::InitializeEx(IBindCtx *,_ITEMIDLIST_ABSOLUTE const *,_PERSIST_FOLDER_TARGET_INFO const *)

- ea: `0x180184bc0`
- end: `0x1801853d7`
- name: `?InitializeEx@CFSFolder@@UEAAJPEAUIBindCtx@@PEBU_ITEMIDLIST_ABSOLUTE@@PEBU_PERSIST_FOLDER_TARGET_INFO@@@Z`
- size: `2071`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, struct IBindCtx *, const struct _ITEMIDLIST_ABSOLUTE *, const struct _PERSIST_FOLDER_TARGET_INFO *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180038f50`
- `0x180045230`
- `0x1800ff160`
- `0x180184bc0`
- `0x1803b1f60`
- `0x1803b69b9`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801852fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801852fd`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18018539b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18018539b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180185213`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180185213`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18018537b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18018537b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1801852ae`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1801852ae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18018534e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18018534e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180185325`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180185325`
- `OLEAUT32!__imp_SysAllocString` at `0x180184c7b`
- `OLEAUT32!__imp_SysAllocString` at `0x180184c7b`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1801851a1`
- `SHCORE!__imp_IUnknown_GetClassID` at `0x1801851a1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184e88`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184ea8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184ec8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184ee8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184efd`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184e88`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184ea8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184ec8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184ee8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180184efd`

## string_xrefs

- `0x180185347`: `%SystemRoot%\System32\RuntimeBroker.exe`
- `0x180184e12`: `ItemCacheContext`
- `0x180184e9d`: `FSFolder_ConvertToSidString`
- `0x180184e7a`: `FSFolder_ResolveSidToUserName`

## pseudocode

```c

```
