# RunScreenSaver(_WLSM_GLOBAL_CONTEXT *,SCREEN_SAVER_DATA *,_WINLOGON_JOB * *)

- ea: `0x140006c3c`
- end: `0x140006fb7`
- name: `?RunScreenSaver@@YAKPEAU_WLSM_GLOBAL_CONTEXT@@PEAUSCREEN_SAVER_DATA@@PEAPEAU_WINLOGON_JOB@@@Z`
- size: `891`
- prototype: `__int64 __fastcall(CSession **, struct SCREEN_SAVER_DATA *, struct _WINLOGON_JOB **)`
- caller_count: `3`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x140003ea0`
- `0x1400045d0`
- `0x14005f6d0`

## callees

- `0x140004f20`
- `0x1400057f4`
- `0x140006c3c`
- `0x140006fc0`
- `0x140008a20`
- `0x14003de48`
- `0x14004e100`
- `0x14004e4ac`
- `0x1400544e0`
- `0x140078b0c`
- `0x1400790d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006ea2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006ea2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140006e98`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x140006e98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006f86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006f96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ce2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ce3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006f86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140006f96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ce2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14009ce3e`
- `ntdll!NtClose` at `0x140006eb6`
- `ntdll!NtClose` at `0x140006eb6`

## pseudocode

```c

```
