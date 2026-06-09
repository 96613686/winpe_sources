# DllGetActivationFactory

- ea: `0x180005d90`
- end: `0x180005f3b`
- name: `DllGetActivationFactory`
- size: `427`
- prototype: `__int64 __fastcall(HSTRING string, _QWORD *Ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002ad0`
- `0x180005a04`
- `0x180005d90`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005dcb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180005dcb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180005dea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180005dea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180005e00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x180005e00`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005ea5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180005ea5`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180005f10`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180005f10`

## string_xrefs

- `0x180005ed9`: `activatibleClassId`

## pseudocode

```c

```
