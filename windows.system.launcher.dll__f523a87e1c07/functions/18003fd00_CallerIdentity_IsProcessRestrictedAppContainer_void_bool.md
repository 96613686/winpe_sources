# CallerIdentity::IsProcessRestrictedAppContainer(void *,bool *)

- ea: `0x18003fd00`
- end: `0x18003fe2f`
- name: `?IsProcessRestrictedAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z`
- size: `303`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, bool *, bool *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800533e4`
- `0x18006831c`

## callees

- `0x18003fd00`
- `0x18008a030`
- `0x18008a9d8`
- `0x1800ea2d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003fd36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003fd36`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003fd4d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003fd4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd57`
- `ntdll!RtlGetAppContainerSidType` at `0x18003fdd6`
- `ntdll!RtlGetAppContainerSidType` at `0x18003fdd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fe05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003fe05`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003fda9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003fda9`

## pseudocode

```c

```
