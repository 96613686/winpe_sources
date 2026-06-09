# FvepIsVolumeEncryptedCached

- ea: `0x18006f910`
- end: `0x18006f9fc`
- name: `FvepIsVolumeEncryptedCached`
- size: `236`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006fa04`

## callees

- `0x18006f274`
- `0x18006f87c`
- `0x18006f910`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18006f9d9`
- `KERNEL32!GetProcessHeap` at `0x18006f9d9`
- `KERNEL32!HeapFree` at `0x18006f9e7`
- `KERNEL32!HeapFree` at `0x18006f9e7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006f99e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006f99e`

## string_xrefs

- `0x18006f979`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\FveDetect\Cache`

## pseudocode

```c

```
