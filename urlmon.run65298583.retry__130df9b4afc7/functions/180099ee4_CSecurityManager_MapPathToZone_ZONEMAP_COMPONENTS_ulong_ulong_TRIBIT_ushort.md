# CSecurityManager::_MapPathToZone(ZONEMAP_COMPONENTS *,ulong *,ulong,TRIBIT *,ushort * *)

- ea: `0x180099ee4`
- end: `0x18009a226`
- name: `?_MapPathToZone@CSecurityManager@@IEAAXPEAVZONEMAP_COMPONENTS@@PEAKKPEAW4TRIBIT@@PEAPEAG@Z`
- size: `834`
- prototype: `void __usercall(CSecurityManager *__hidden this@<rcx>, struct ZONEMAP_COMPONENTS *@<rdx>, unsigned int *@<r8>, unsigned int@<r9d>, enum TRIBIT *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180099afc`
- `0x1800ffddc`

## callees

- `0x1800215c0`
- `0x180029a90`
- `0x1800308c0`
- `0x18004721c`
- `0x18006db6c`
- `0x180099978`
- `0x180099ee4`
- `0x1801021e4`
- `0x18011ba6e`
- `0x18011baa0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180099f7a`
- `msvcrt!_wcsnicmp` at `0x18009a00d`
- `msvcrt!_wcsnicmp` at `0x18009a081`
- `msvcrt!_wcsnicmp` at `0x180099f7a`
- `msvcrt!_wcsnicmp` at `0x18009a00d`
- `msvcrt!_wcsnicmp` at `0x18009a081`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18009a0e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18009a0e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a03d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a0af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a1f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a03d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a0af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a1f6`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18009a186`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x18009a186`

## pseudocode

```c

```
