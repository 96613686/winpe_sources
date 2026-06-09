# DllGetActivationFactory

- ea: `0x180016640`
- end: `0x1800169b2`
- name: `DllGetActivationFactory`
- size: `882`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180016640`
- `0x180054130`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016676`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180016676`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800167b3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800167b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016942`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016942`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016805`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001695c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016805`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001695c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800168d2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800168d2`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800167cf`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001691f`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x1800167cf`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001691f`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800168f2`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x1800168f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180016697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180016697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800166e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800166e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800166b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x1800166b3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180016875`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180016875`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016975`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016975`

## string_xrefs

- `0x180016840`: `activatibleClassId`

## pseudocode

```c

```
