# CNetFolder::_GetPathForShare(IDNETRESOURCE const *,ushort *,ulong)

- ea: `0x1800f5f20`
- end: `0x1800f6156`
- name: `?_GetPathForShare@CNetFolder@@AEAAJPEBUIDNETRESOURCE@@PEAGK@Z`
- size: `566`
- prototype: `__int64 __fastcall(CNetFolder *__hidden this, const struct IDNETRESOURCE *, unsigned __int16 *, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18005dc80`
- `0x1800f4ad0`
- `0x1800f58f0`
- `0x1801018b0`
- `0x1802b21fc`

## callees

- `0x1800f5844`
- `0x1800f5f20`
- `0x1800f6160`
- `0x180133f50`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180666dec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180666dec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180666f05`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180666f05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180666da9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180666da9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180666eca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180666eca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f5f56`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f5f56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6073`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6073`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180666dbf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180666dbf`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800f5fec`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800f5fec`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800f5ffb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800f6121`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800f5ffb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x1800f6121`
- `SHCORE!__imp_ualstrcpynW` at `0x1800f610d`
- `SHCORE!__imp_ualstrcpynW` at `0x1800f610d`
- `MPR!WNetUseConnectionW` at `0x180666e9c`
- `MPR!WNetUseConnectionW` at `0x180666e9c`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800f5fb6`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x1800f5fb6`

## pseudocode

```c

```
