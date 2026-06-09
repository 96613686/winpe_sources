# Windows::Internal::CCustomPopupWindowImpl::_ComputeWindowRect(tagSIZE const &,Windows::UI::Immersive::CConstraint const &,bool)

- ea: `0x1800acf10`
- end: `0x1800ad1bb`
- name: `?_ComputeWindowRect@CCustomPopupWindowImpl@Internal@Windows@@AEAA?AUtagRECT@@AEBUtagSIZE@@AEBVCConstraint@Immersive@UI@3@_N@Z`
- size: `683`
- prototype: `struct tagRECT *(Windows::Internal::CCustomPopupWindowImpl *__hidden this, struct tagRECT *__return_ptr __struct_ptr retstr, const struct tagSIZE *, const struct Windows::UI::Immersive::CConstraint *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800acce0`

## callees

- `0x18004bba4`
- `0x180054130`
- `0x1800ac0ac`
- `0x1800acf10`
- `0x1800ed010`

## import_xrefs

- `USER32!GetClientRect` at `0x1800acff9`
- `USER32!GetClientRect` at `0x1800acff9`
- `USER32!MonitorFromRect` at `0x1800acf4b`
- `USER32!MonitorFromRect` at `0x1800acf4b`
- `USER32!GetMonitorInfoW` at `0x1800acfb7`
- `USER32!GetMonitorInfoW` at `0x1800acfb7`
- `USER32!MapWindowPoints` at `0x1800ad022`
- `USER32!MapWindowPoints` at `0x1800ad022`

## pseudocode

```c

```
