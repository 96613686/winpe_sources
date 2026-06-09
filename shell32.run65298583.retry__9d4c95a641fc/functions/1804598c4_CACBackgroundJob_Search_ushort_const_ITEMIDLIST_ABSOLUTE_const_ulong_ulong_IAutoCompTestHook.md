# CACBackgroundJob::_Search(ushort const *,_ITEMIDLIST_ABSOLUTE const *,ulong,ulong,IAutoCompTestHook *)

- ea: `0x1804598c4`
- end: `0x180459d78`
- name: `?_Search@CACBackgroundJob@@IEAAXPEBGPEBU_ITEMIDLIST_ABSOLUTE@@KKPEAUIAutoCompTestHook@@@Z`
- size: `1204`
- prototype: `void __usercall(CACBackgroundJob *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const struct _ITEMIDLIST_ABSOLUTE *@<r8>, unsigned int@<r9d>, unsigned int, struct IAutoCompTestHook *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1804591ac`

## callees

- `0x180019f6c`
- `0x18001ba80`
- `0x1800257d0`
- `0x1800270a0`
- `0x1800a28ac`
- `0x180105b48`
- `0x1801a0dd0`
- `0x1801d0728`
- `0x180233280`
- `0x1804592ec`
- `0x1804593a8`
- `0x1804598c4`
- `0x180571010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1804599d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1804599d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180459c6d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180459c6d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180459a03`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180459c50`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180459c79`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180459a03`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180459c50`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180459c79`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180459c92`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180459c92`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180459a66`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180459a66`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180459c0e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180459c0e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180459b3d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180459b3d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180459ab9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180459ada`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180459af4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180459b94`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180459ab9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180459ada`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180459af4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNW` at `0x180459b94`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x180459b12`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x180459baa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x180459b12`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNIW` at `0x180459baa`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804599ba`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1804599ba`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180459b5f`
- `api-ms-win-core-url-l1-1-0!PathCreateFromUrlW` at `0x180459b5f`
- `USER32!RegisterWindowMessageA` at `0x180459ccd`
- `USER32!RegisterWindowMessageA` at `0x180459d27`
- `USER32!RegisterWindowMessageA` at `0x180459ccd`
- `USER32!RegisterWindowMessageA` at `0x180459d27`
- `USER32!PostMessageW` at `0x180459d02`
- `USER32!PostMessageW` at `0x180459d3c`
- `USER32!PostMessageW` at `0x180459d02`
- `USER32!PostMessageW` at `0x180459d3c`

## string_xrefs

- `0x180459cc6`: `AC_SearchComplete`
- `0x180459d20`: `AC_SearchComplete`

## pseudocode

```c

```
