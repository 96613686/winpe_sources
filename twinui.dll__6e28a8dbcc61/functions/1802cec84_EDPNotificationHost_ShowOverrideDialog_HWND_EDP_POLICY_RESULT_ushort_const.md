# EDPNotificationHost::_ShowOverrideDialog(HWND__ *,EDP_POLICY_RESULT,ushort const *)

- ea: `0x1802cec84`
- end: `0x1802cef83`
- name: `?_ShowOverrideDialog@EDPNotificationHost@@AEAAJPEAUHWND__@@W4EDP_POLICY_RESULT@@PEBG@Z`
- size: `767`
- prototype: `int __high(HWND, enum EDP_POLICY_RESULT, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1802ce9b0`

## callees

- `0x18000b7e8`
- `0x18003c5e4`
- `0x180138e34`
- `0x18013d330`
- `0x1802cec84`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802ceecd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1802ceecd`
- `USER32!MonitorFromWindow` at `0x1802ced85`
- `USER32!MonitorFromWindow` at `0x1802ced85`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802cecf6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802cecf6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1802ceef9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x1802ceef9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1802ceeef`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x1802ceeef`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1802ceebd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1802cef1f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1802ceebd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1802cef1f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802cedcd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802cedcd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1802ced09`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x1802ced09`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1802ceddd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1802ceddd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x1802cef0b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetMessageW` at `0x1802cef0b`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1802ceda9`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1802ceda9`

## pseudocode

```c

```
