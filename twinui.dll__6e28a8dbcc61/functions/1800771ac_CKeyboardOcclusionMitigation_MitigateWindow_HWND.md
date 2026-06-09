# CKeyboardOcclusionMitigation::_MitigateWindow(HWND__ *)

- ea: `0x1800771ac`
- end: `0x1800776b3`
- name: `?_MitigateWindow@CKeyboardOcclusionMitigation@@AEAA_NPEAUHWND__@@@Z`
- size: `1287`
- prototype: `bool __fastcall(CKeyboardOcclusionMitigation *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `24`
- tags: `service_task`

## callers

- `0x180077180`
- `0x18010fd20`

## callees

- `0x18000b7e8`
- `0x18002a96c`
- `0x18002b04c`
- `0x18006e318`
- `0x1800771ac`
- `0x180081f44`
- `0x18008275c`
- `0x180107ca4`
- `0x18013d330`
- `0x18013df8c`
- `0x180258db8`
- `0x180258f48`
- `0x180259214`
- `0x180259268`
- `0x180259944`
- `0x18025a230`
- `0x18025a30c`
- `0x18025a330`
- `0x18025a3d0`
- `0x18025a490`
- `0x18025a4d4`
- `0x18025a5c4`
- `0x18025a8c8`
- `0x1803a3010`

## import_xrefs

- `USER32!GetWindowPlacement` at `0x180077406`
- `USER32!GetWindowPlacement` at `0x180077406`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x1800775e0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x1800775e0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x180077287`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1800772d3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x180077287`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x1800772d3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x180077307`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x180077429`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x180077307`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x180077429`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellFrameWindow` at `0x180077536`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellFrameWindow` at `0x180077536`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180077575`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x180077575`
- `dwmapi!DwmGetWindowAttribute` at `0x1800772b2`
- `dwmapi!DwmGetWindowAttribute` at `0x1800772b2`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1800772e5`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x1800772e5`

## pseudocode

```c

```
