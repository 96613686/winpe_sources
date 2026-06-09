# CThreadHook::s_CallWndProc(int,unsigned __int64,__int64)

- ea: `0x18002acc0`
- end: `0x18002b1da`
- name: `?s_CallWndProc@CThreadHook@@CA_JH_K_J@Z`
- size: `1306`
- prototype: `LRESULT __stdcall(int code, WPARAM wParam, LPARAM lParam)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18001c82c`
- `0x18002acc0`
- `0x18002b1e0`
- `0x18002b220`
- `0x18002b280`
- `0x180068720`
- `0x180068c9c`
- `0x180068d08`
- `0x180092464`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002aceb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002aceb`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x18002b10b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterWindowMessageW` at `0x18002b10b`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!CallNextHookEx` at `0x18002afe2`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!CallNextHookEx` at `0x18002afe2`

## pseudocode

```c

```
