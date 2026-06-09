# DllGetActivationFactory

- ea: `0x18001e4e0`
- end: `0x18001e7e8`
- name: `DllGetActivationFactory`
- size: `776`
- prototype: `__int64 __fastcall(HSTRING string)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001e4e0`
- `0x1800c73c0`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e633`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001e633`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e679`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e786`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e679`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001e786`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e768`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e768`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e739`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e739`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001e519`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001e519`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001e649`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001e791`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001e649`
- `api-ms-win-core-util-l1-1-0!DecodePointer` at `0x18001e791`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001e753`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001e753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e568`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001e534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18001e534`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001e54a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001e54a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e7d7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001e7d7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001e6d8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x18001e6d8`

## string_xrefs

- `0x18001e6a3`: `activatibleClassId`

## pseudocode

```c

```
