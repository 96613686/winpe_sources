# Windows::Internal::XamlPopupWindowImpl::_ComputeWindowRect(tagSIZE const &,Windows::UI::Immersive::CConstraint const &,bool)

- ea: `0x18002c930`
- end: `0x18002cbfa`
- name: `?_ComputeWindowRect@XamlPopupWindowImpl@Internal@Windows@@AEAA?AUtagRECT@@AEBUtagSIZE@@AEBVCConstraint@Immersive@UI@3@_N@Z`
- size: `714`
- prototype: `struct tagRECT *__fastcall(Windows::Internal::XamlPopupWindowImpl *__hidden this, struct tagRECT *__return_ptr __struct_ptr retstr, const struct tagSIZE *, const struct Windows::UI::Immersive::CConstraint *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002c47c`

## callees

- `0x18002c930`
- `0x18003666c`
- `0x18004aeb0`
- `0x180054130`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c993`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002c993`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c9b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002c9b2`
- `USER32!GetClientRect` at `0x18002ca35`
- `USER32!GetClientRect` at `0x18002ca35`
- `USER32!MonitorFromRect` at `0x18002c96b`
- `USER32!MonitorFromRect` at `0x18002c96b`
- `USER32!GetMonitorInfoW` at `0x18002c9ff`
- `USER32!GetMonitorInfoW` at `0x18002c9ff`
- `USER32!MapWindowPoints` at `0x18002ca5a`
- `USER32!MapWindowPoints` at `0x18002ca5a`

## pseudocode

```c

```
