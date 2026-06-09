# DetermineTracingDirectoryPath

- ea: `0x1800ba300`
- end: `0x1800ba413`
- name: `DetermineTracingDirectoryPath`
- size: `275`
- prototype: `__int64 __fastcall(__int64, WCHAR **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800ba448`

## callees

- `0x1800ba300`
- `0x1800ba9a0`
- `0x1800bad78`

## import_xrefs

- `ntdll!RtlGetSuiteMask` at `0x1800ba326`
- `ntdll!RtlGetSuiteMask` at `0x1800ba326`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ba347`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ba3b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ba347`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ba3b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba3ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba3f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba3ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ba3f8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ba39f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ba3cc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ba39f`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ba3cc`

## string_xrefs

- `0x1800ba370`: `%ProgramData%\LogFiles`
- `0x1800ba380`: `%windir%\system32\LogFiles`

## pseudocode

```c

```
