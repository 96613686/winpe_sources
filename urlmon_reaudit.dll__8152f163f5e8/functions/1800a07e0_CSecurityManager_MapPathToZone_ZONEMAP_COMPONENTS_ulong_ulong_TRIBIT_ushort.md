# CSecurityManager::_MapPathToZone(ZONEMAP_COMPONENTS *,ulong *,ulong,TRIBIT *,ushort * *)

- ea: `0x1800a07e0`
- end: `0x1800a0b53`
- name: `?_MapPathToZone@CSecurityManager@@IEAAXPEAVZONEMAP_COMPONENTS@@PEAKKPEAW4TRIBIT@@PEAPEAG@Z`
- size: `883`
- prototype: `void __usercall(CSecurityManager *__hidden this@<rcx>, struct ZONEMAP_COMPONENTS *@<rdx>, unsigned int *@<r8>, unsigned int@<r9d>, enum TRIBIT *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800a03ec`
- `0x18010ae70`

## callees

- `0x180012d10`
- `0x180028510`
- `0x180031600`
- `0x180059320`
- `0x180073088`
- `0x1800a0264`
- `0x1800a07e0`
- `0x18010d374`
- `0x18012862e`
- `0x180128660`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800a0876`
- `msvcrt!_wcsnicmp` at `0x1800a090f`
- `msvcrt!_wcsnicmp` at `0x1800a098f`
- `msvcrt!_wcsnicmp` at `0x1800a0876`
- `msvcrt!_wcsnicmp` at `0x1800a090f`
- `msvcrt!_wcsnicmp` at `0x1800a098f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1800a0a00`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x1800a0a00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0945`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a09c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0b1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0945`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a09c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0b1c`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1800a0aa6`
- `api-ms-win-shlwapi-ie-l1-1-0!PathFileExistsAndAttributesW` at `0x1800a0aa6`

## pseudocode

```c

```
