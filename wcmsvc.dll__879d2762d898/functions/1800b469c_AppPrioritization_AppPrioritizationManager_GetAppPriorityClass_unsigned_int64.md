# AppPrioritization::AppPrioritizationManager::GetAppPriorityClass(unsigned __int64)

- ea: `0x1800b469c`
- end: `0x1800b4775`
- name: `?GetAppPriorityClass@AppPrioritizationManager@AppPrioritization@@CAI_K@Z`
- size: `217`
- prototype: `unsigned int __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18006aa48`

## callees

- `0x18003a540`
- `0x18003cacc`
- `0x1800b469c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b46cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4722`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b46cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4722`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x1800b470b`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x1800b470b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b46ac`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800b46ac`

## pseudocode

```c

```
