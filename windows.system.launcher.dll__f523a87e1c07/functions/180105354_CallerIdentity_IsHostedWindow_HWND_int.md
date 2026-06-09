# CallerIdentity::IsHostedWindow(HWND__ *,int *)

- ea: `0x180105354`
- end: `0x1801054a8`
- name: `?IsHostedWindow@CallerIdentity@@YAJPEAUHWND__@@PEAH@Z`
- size: `340`
- prototype: `__int64 __fastcall(HWND hWnd, HWND, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e6780`

## callees

- `0x18008a030`
- `0x180105354`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801053dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801053dc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180105421`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180105421`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180105459`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180105459`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801053c4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1801053c4`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x1801053ea`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180105440`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x1801053ea`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180105440`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x18010546f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindow` at `0x18010546f`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18010540b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18010540b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x18010539b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x18010539b`

## pseudocode

```c

```
