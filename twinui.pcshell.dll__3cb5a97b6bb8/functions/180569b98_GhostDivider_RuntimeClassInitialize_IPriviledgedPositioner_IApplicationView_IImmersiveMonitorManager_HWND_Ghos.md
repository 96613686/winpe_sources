# GhostDivider::RuntimeClassInitialize(IPriviledgedPositioner *,IApplicationView *,IImmersiveMonitorManager *,HWND__ *,GhostDividerPlacement,GhostDividerSize)

- ea: `0x180569b98`
- end: `0x180569fe5`
- name: `?RuntimeClassInitialize@GhostDivider@@QEAAJPEAUIPriviledgedPositioner@@PEAUIApplicationView@@PEAUIImmersiveMonitorManager@@PEAUHWND__@@W4GhostDividerPlacement@@W4GhostDividerSize@@@Z`
- size: `1101`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802a3cd8`

## callees

- `0x1800134f8`
- `0x1800237c8`
- `0x1800726b8`
- `0x1802bbaf8`
- `0x1802cf1c8`
- `0x1802d0518`
- `0x180356360`
- `0x180569b4c`
- `0x180569b98`
- `0x1806fa010`

## import_xrefs

- `USER32!CreateWindowExW` at `0x180569dc8`
- `USER32!CreateWindowExW` at `0x180569dc8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180569f25`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180569f25`
- `api-ms-win-shcore-scaling-l1-1-1!GetScaleFactorForMonitor` at `0x180569ca4`
- `api-ms-win-shcore-scaling-l1-1-1!GetScaleFactorForMonitor` at `0x180569ca4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180569ef5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180569ef5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180569eb6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180569eb6`
- `ext-ms-win-ntuser-window-l1-1-1!SetLayeredWindowAttributes` at `0x180569e00`
- `ext-ms-win-ntuser-window-l1-1-1!SetLayeredWindowAttributes` at `0x180569e00`
- `ext-ms-win-ntuser-private-l1-1-1!SetWindowCompositionAttribute` at `0x180569e6e`
- `ext-ms-win-ntuser-private-l1-1-1!SetWindowCompositionAttribute` at `0x180569e6e`
- `ext-ms-win-uxtheme-themes-l1-1-0!__imp_GetIsImmersiveColorUsingHighContrast` at `0x180569e0f`
- `ext-ms-win-uxtheme-themes-l1-1-0!__imp_GetIsImmersiveColorUsingHighContrast` at `0x180569e0f`
- `ext-ms-win-dwmapi-ext-l1-1-0!DwmSetWindowAttribute` at `0x180569e8b`
- `ext-ms-win-dwmapi-ext-l1-1-0!DwmSetWindowAttribute` at `0x180569e8b`

## pseudocode

```c

```
