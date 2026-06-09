# FlowUIBase::InitializeUI(HWND__ *,long,IPopupWindow *,IDataTransferBroker *,IUnknown *)

- ea: `0x1802f68f0`
- end: `0x1802f6ce6`
- name: `?InitializeUI@FlowUIBase@@UEAAJPEAUHWND__@@JPEAUIPopupWindow@@PEAUIDataTransferBroker@@PEAUIUnknown@@@Z`
- size: `1014`
- prototype: `__int64 __usercall@<rax>(FlowUIBase *__hidden this@<rcx>, HWND hWnd@<rdx>, int@<r8d>, struct IPopupWindow *@<r9>, struct IDataTransferBroker *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18038d220`
- `0x180390bf0`

## callees

- `0x18000b7e8`
- `0x18001f3c0`
- `0x18008c65c`
- `0x18008e9d4`
- `0x18009f240`
- `0x1800e6b28`
- `0x18013d330`
- `0x180153020`
- `0x1802eb4fc`
- `0x1802f5390`
- `0x1802f5414`
- `0x1802f5488`
- `0x1802f68f0`
- `0x1802f89d8`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802f6a34`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802f6a34`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802f6c55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1802f6c55`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802f6a92`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1802f6a92`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802f6963`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetAncestor` at `0x1802f6963`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1802f6ad7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1802f6af7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1802f6ad7`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1802f6af7`
- `DUI70!StrToID` at `0x1802f6acb`
- `DUI70!StrToID` at `0x1802f6aeb`
- `DUI70!StrToID` at `0x1802f6acb`
- `DUI70!StrToID` at `0x1802f6aeb`

## pseudocode

```c

```
