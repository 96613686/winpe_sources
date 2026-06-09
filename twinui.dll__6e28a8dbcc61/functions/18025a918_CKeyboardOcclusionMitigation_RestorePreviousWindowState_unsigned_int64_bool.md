# CKeyboardOcclusionMitigation::_RestorePreviousWindowState(unsigned __int64,bool)

- ea: `0x18025a918`
- end: `0x18025ab85`
- name: `?_RestorePreviousWindowState@CKeyboardOcclusionMitigation@@AEAA_N_K_N@Z`
- size: `621`
- prototype: `bool __fastcall(CKeyboardOcclusionMitigation *__hidden this, unsigned __int64, bool)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task`

## callers

- `0x1800a4578`
- `0x18010fd20`

## callees

- `0x18000b7e8`
- `0x180081f44`
- `0x18008275c`
- `0x1800f91c0`
- `0x1800f91e4`
- `0x18013d330`
- `0x180259740`
- `0x180259790`
- `0x1802597d8`
- `0x18025a490`
- `0x18025a4d4`
- `0x18025a5c4`
- `0x18025a750`
- `0x18025a918`
- `0x1803a3010`

## import_xrefs

- `USER32!SetWindowPlacement` at `0x18025aaa8`
- `USER32!SetWindowPlacement` at `0x18025ab7a`
- `USER32!SetWindowPlacement` at `0x18025aaa8`
- `USER32!SetWindowPlacement` at `0x18025ab7a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18025aaec`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x18025aaec`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18025a98b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x18025a98b`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18025aa82`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18025aa82`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellFrameWindow` at `0x18025a9ec`
- `ext-ms-win-ntuser-private-l1-1-1!__imp_IsShellFrameWindow` at `0x18025a9ec`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18025aa2c`
- `twinapi.appcore!__imp_CoreQueryWindowService` at `0x18025aa2c`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18025a9b5`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x18025a9b5`

## pseudocode

```c

```
