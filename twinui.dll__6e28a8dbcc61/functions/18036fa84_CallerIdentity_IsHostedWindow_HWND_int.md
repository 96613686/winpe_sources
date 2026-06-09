# CallerIdentity::IsHostedWindow(HWND__ *,int *)

- ea: `0x18036fa84`
- end: `0x18036fbd8`
- name: `?IsHostedWindow@CallerIdentity@@YAJPEAUHWND__@@PEAH@Z`
- size: `340`
- prototype: `__int64 __fastcall(HWND hWnd, HWND, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18033d750`

## callees

- `0x18013d330`
- `0x18036fa84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18036fb0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18036fb0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18036fb89`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18036fb89`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18036faf4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18036faf4`
- `USER32!__imp_GetProcessUIContextInformation` at `0x18036fb1a`
- `USER32!__imp_GetProcessUIContextInformation` at `0x18036fb70`
- `USER32!__imp_GetProcessUIContextInformation` at `0x18036fb1a`
- `USER32!__imp_GetProcessUIContextInformation` at `0x18036fb70`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18036fb51`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18036fb51`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18036fb3b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18036fb3b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x18036facb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x18036facb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x18036fb9f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x18036fb9f`

## pseudocode

```c

```
