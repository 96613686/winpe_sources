# DllGetActivationFactory

- ea: `0x18001b5b0`
- end: `0x18001b8c1`
- name: `DllGetActivationFactory`
- size: `785`
- prototype: `__int64 __fastcall(HSTRING string, PVOID *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001b5b0`
- `0x18008a030`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001b5e9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001b5e9`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001b823`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001b823`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001b719`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001b861`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001b719`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001b861`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b749`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b856`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b749`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001b856`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b809`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b809`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b838`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b838`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b703`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001b703`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001b61a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001b61a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001b604`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001b604`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b638`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001b638`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001b7a8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001b7a8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001b8b0`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001b8b0`

## string_xrefs

- `0x18001b773`: `activatibleClassId`

## pseudocode

```c

```
