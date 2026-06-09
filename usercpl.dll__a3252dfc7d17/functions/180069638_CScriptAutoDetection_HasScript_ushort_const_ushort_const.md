# CScriptAutoDetection::HasScript(ushort const *,ushort const *)

- ea: `0x180069638`
- end: `0x180069792`
- name: `?HasScript@CScriptAutoDetection@@QEAAJPEBG0@Z`
- size: `346`
- prototype: `__int64 __fastcall(PMAPPING_SERVICE_INFO *prgServices, LPCWSTR pszText, PCWSTR pszFirst)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180069798`

## callees

- `0x180069638`
- `0x18007728a`

## import_xrefs

- `SHLWAPI!StrStrIW` at `0x180069751`
- `SHLWAPI!StrStrIW` at `0x180069751`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800696d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800696d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006967f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006967f`
- `elscore!MappingGetServices` at `0x1800696b4`
- `elscore!MappingGetServices` at `0x1800696b4`
- `elscore!MappingRecognizeText` at `0x180069722`
- `elscore!MappingRecognizeText` at `0x180069722`
- `elscore!MappingFreePropertyBag` at `0x180069776`
- `elscore!MappingFreePropertyBag` at `0x180069776`

## pseudocode

```c

```
