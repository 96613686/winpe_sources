# DllGetActivationFactory

- ea: `0x18000c0f0`
- end: `0x18000c3fb`
- name: `DllGetActivationFactory`
- size: `779`
- prototype: `__int64 __fastcall(HSTRING string, PVOID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000c0f0`
- `0x18000c8e0`
- `0x180012360`
- `0x18002b1b0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000c12c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000c12c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c291`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000c291`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c2dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000c2dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c33d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000c33d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c1d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c1d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000c147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18000c147`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000c1be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18000c1be`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000c359`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000c359`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c2ac`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c380`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c2ac`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18000c380`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000c3da`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000c3da`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000c186`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18000c186`

## string_xrefs

- `0x18000c151`: `activatibleClassId`

## pseudocode

```c

```
