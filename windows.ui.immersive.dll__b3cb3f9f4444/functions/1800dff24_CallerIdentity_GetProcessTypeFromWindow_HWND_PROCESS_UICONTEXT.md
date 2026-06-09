# CallerIdentity::GetProcessTypeFromWindow(HWND__ *,PROCESS_UICONTEXT *)

- ea: `0x1800dff24`
- end: `0x1800dffda`
- name: `?GetProcessTypeFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAW4PROCESS_UICONTEXT@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, HWND, enum PROCESS_UICONTEXT *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800d47bc`

## callees

- `0x18003d244`
- `0x1800dff24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800dff69`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800dff69`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dffbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dffbb`
- `USER32!GetWindowThreadProcessId` at `0x1800dff42`
- `USER32!GetWindowThreadProcessId` at `0x1800dff42`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800dff99`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800dff99`

## pseudocode

```c

```
