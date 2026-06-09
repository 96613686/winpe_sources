# CDUIViewFrame::SetShellView(IShellView *,HWND__ *,IUnknown *,SETVIEWFLAGS)

- ea: `0x180091c60`
- end: `0x180091fca`
- name: `?SetShellView@CDUIViewFrame@@UEAAJPEAUIShellView@@PEAUHWND__@@PEAUIUnknown@@W4SETVIEWFLAGS@@@Z`
- size: `874`
- prototype: `int __high(struct IShellView *, HWND, struct IUnknown *, enum SETVIEWFLAGS)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800909d0`

## callees

- `0x18000f5a4`
- `0x180091c60`
- `0x180092150`
- `0x1800923f0`
- `0x180092480`
- `0x180092528`
- `0x180092634`
- `0x18009277c`
- `0x1800c7228`
- `0x180233280`
- `0x18033a450`
- `0x180571010`

## import_xrefs

- `USER32!SetWindowPos` at `0x180091e0a`
- `USER32!SetWindowPos` at `0x180091e0a`
- `USER32!SetWindowTextW` at `0x180091ec9`
- `USER32!SetWindowTextW` at `0x180091ec9`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180091f88`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180091f88`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180091d68`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180091dbc`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180091f28`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180091d68`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180091dbc`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x180091f28`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180091e6e`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180091e6e`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180091e52`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x180091e52`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180091e62`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x180091e62`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180091eda`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180091ef6`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180091eda`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180091ef6`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180091caf`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180091caf`
- `DUI70!EnableAnimations` at `0x180091ee4`
- `DUI70!EnableAnimations` at `0x180091ee4`
- `DUI70!DisableAnimations` at `0x180091c8f`
- `DUI70!DisableAnimations` at `0x180091c8f`

## pseudocode

```c

```
