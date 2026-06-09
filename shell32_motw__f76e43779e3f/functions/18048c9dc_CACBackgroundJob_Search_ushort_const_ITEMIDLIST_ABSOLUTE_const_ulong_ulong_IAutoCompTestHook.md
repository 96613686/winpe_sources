# CACBackgroundJob::_Search(ushort const *,_ITEMIDLIST_ABSOLUTE const *,ulong,ulong,IAutoCompTestHook *)

- ea: `0x18048c9dc`
- end: `0x18048cf13`
- name: `?_Search@CACBackgroundJob@@IEAAXPEBGPEBU_ITEMIDLIST_ABSOLUTE@@KKPEAUIAutoCompTestHook@@@Z`
- size: `1335`
- prototype: `void __usercall(CACBackgroundJob *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const struct _ITEMIDLIST_ABSOLUTE *@<r8>, unsigned int@<r9d>, unsigned int, struct IAutoCompTestHook *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18048c1d0`

## callees

- `0x18001abf8`
- `0x180065048`
- `0x1800662c0`
- `0x1800a0a44`
- `0x1800b2a34`
- `0x180114b7c`
- `0x1801b53b8`
- `0x1801e7280`
- `0x180249490`
- `0x18048c344`
- `0x18048c414`
- `0x18048c9dc`
- `0x1805b2010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18048caee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18048caee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18048cddd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18048cddd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18048ce0e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18048ce0e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18048cb27`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18048cdba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18048cdef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18048cb27`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18048cdba`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18048cdef`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18048cb90`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18048cb90`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18048cd72`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18048cd72`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18048cbe9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18048cc10`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18048cc30`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18048ccec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18048cbe9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18048cc10`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18048cc30`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x18048ccec`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18048cc58`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18048cd08`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18048cc58`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x18048cd08`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18048cc89`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18048cc89`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18048cad2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18048cad2`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18048ccb1`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x18048ccb1`
- `USER32!RegisterWindowMessageA` at `0x18048ce4f`
- `USER32!RegisterWindowMessageA` at `0x18048ceb5`
- `USER32!RegisterWindowMessageA` at `0x18048ce4f`
- `USER32!RegisterWindowMessageA` at `0x18048ceb5`
- `USER32!PostMessageW` at `0x18048ce8a`
- `USER32!PostMessageW` at `0x18048ced0`
- `USER32!PostMessageW` at `0x18048ce8a`
- `USER32!PostMessageW` at `0x18048ced0`

## string_xrefs

- `0x18048ce48`: `AC_SearchComplete`
- `0x18048ceae`: `AC_SearchComplete`

## pseudocode

```c

```
