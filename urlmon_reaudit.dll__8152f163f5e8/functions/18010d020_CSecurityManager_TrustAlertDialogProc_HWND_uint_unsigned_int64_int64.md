# CSecurityManager::TrustAlertDialogProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18010d020`
- end: `0x18010d36b`
- name: `?TrustAlertDialogProc@CSecurityManager@@SA_JPEAUHWND__@@I_K_J@Z`
- size: `843`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18005bc6c`
- `0x1800a25dc`
- `0x18010ae24`
- `0x18010cb8c`
- `0x18010cc90`
- `0x18010d020`
- `0x180116830`
- `0x18011c5fc`
- `0x18012506c`
- `0x180125198`
- `0x1801252ac`
- `0x180129010`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010d324`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18010d324`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18010d0a2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18010d0a2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010d0e4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18010d0e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010d0c0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18010d0c0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18010d1a2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18010d1a2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18010d080`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18010d164`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18010d080`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongPtrW` at `0x18010d164`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18010d2ce`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetForegroundWindow` at `0x18010d2ce`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x18010d125`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!IsWindowVisible` at `0x18010d125`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18010d2f5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18010d2f5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18010d2b8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18010d2b8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x18010d241`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x18010d241`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18010d189`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18010d189`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18010d116`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18010d230`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18010d2a7`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18010d116`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18010d230`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18010d2a7`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CheckDlgButton` at `0x18010d222`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!CheckDlgButton` at `0x18010d222`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18010d144`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18010d144`

## pseudocode

```c

```
