# CDUIViewFrame::SetShellView(IShellView *,HWND__ *,IUnknown *,SETVIEWFLAGS)

- ea: `0x180086fa0`
- end: `0x180087362`
- name: `?SetShellView@CDUIViewFrame@@UEAAJPEAUIShellView@@PEAUHWND__@@PEAUIUnknown@@W4SETVIEWFLAGS@@@Z`
- size: `962`
- prototype: `int __high(struct IShellView *, HWND, struct IUnknown *, enum SETVIEWFLAGS)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180085bc0`

## callees

- `0x18000fc30`
- `0x180086fa0`
- `0x180087510`
- `0x1800877d4`
- `0x180087868`
- `0x18008791c`
- `0x180087a30`
- `0x180087b9c`
- `0x1800c80b8`
- `0x180249490`
- `0x18035be60`
- `0x1805b2010`

## import_xrefs

- `USER32!SetWindowPos` at `0x180087162`
- `USER32!SetWindowPos` at `0x180087162`
- `USER32!SetWindowTextW` at `0x180087239`
- `USER32!SetWindowTextW` at `0x180087239`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800870b4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18008710e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800872b1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800870b4`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18008710e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x1800872b1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18008731a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18008731a`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800871d8`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x1800871d8`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800871b0`
- `DUI70!?SetLayoutPos@Element@DirectUI@@QEAAJH@Z` at `0x1800871b0`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800871c6`
- `DUI70!?SetID@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800871c6`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180087250`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180087278`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180087250`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180087278`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180086ff5`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180086ff5`
- `DUI70!EnableAnimations` at `0x180087260`
- `DUI70!EnableAnimations` at `0x180087260`
- `DUI70!DisableAnimations` at `0x180086fcf`
- `DUI70!DisableAnimations` at `0x180086fcf`

## pseudocode

```c

```
