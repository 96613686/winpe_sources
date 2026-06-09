# Windows::Internal::CPopupWindowImpl::_ComputeWindowRect(tagSIZE const &,Windows::UI::Immersive::CConstraint const &,bool)

- ea: `0x180023384`
- end: `0x180023654`
- name: `?_ComputeWindowRect@CPopupWindowImpl@Internal@Windows@@AEAA?AUtagRECT@@AEBUtagSIZE@@AEBVCConstraint@Immersive@UI@3@_N@Z`
- size: `720`
- prototype: `struct tagRECT *(Windows::Internal::CPopupWindowImpl *__hidden this, struct tagRECT *__return_ptr __struct_ptr retstr, const struct tagSIZE *, const struct Windows::UI::Immersive::CConstraint *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180022bf0`

## callees

- `0x180023384`
- `0x18004bba4`
- `0x180054130`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800233e7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800233e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180023406`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180023406`
- `USER32!GetClientRect` at `0x180023482`
- `USER32!GetClientRect` at `0x180023482`
- `USER32!MonitorFromRect` at `0x1800233bf`
- `USER32!MonitorFromRect` at `0x1800233bf`
- `USER32!GetMonitorInfoW` at `0x180023441`
- `USER32!GetMonitorInfoW` at `0x180023441`
- `USER32!MapWindowPoints` at `0x1800234ae`
- `USER32!MapWindowPoints` at `0x1800234ae`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18002346f`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180023491`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x18002346f`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180023491`

## pseudocode

```c

```
