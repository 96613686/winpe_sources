# CProcess::ActivateProcessIfNeeded(_PSM_ACTIVATE_BACKGROUND_TYPE)

- ea: `0x180053950`
- end: `0x180053ceb`
- name: `?ActivateProcessIfNeeded@CProcess@@QEAAJW4_PSM_ACTIVATE_BACKGROUND_TYPE@@@Z`
- size: `923`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000866c`

## callees

- `0x180025250`
- `0x180025310`
- `0x1800297e0`
- `0x180029a8c`
- `0x18002ba28`
- `0x180034540`
- `0x180053950`
- `0x180059be4`
- `0x18005ba08`
- `0x18005c08c`
- `0x18005c11c`
- `0x18007e3d4`
- `0x18008e98c`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x180053bd9`
- `ntdll!NtSetSystemInformation` at `0x180053bd9`
- `ntdll!NtQueryInformationProcess` at `0x180053b22`
- `ntdll!NtQueryInformationProcess` at `0x180053b22`
- `ntdll!RtlNtStatusToDosError` at `0x180053ca6`
- `ntdll!RtlNtStatusToDosError` at `0x180053ca6`
- `RPCRT4!NdrClientCall2` at `0x180053b6e`
- `RPCRT4!NdrClientCall2` at `0x180053b6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053be3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053be3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180053986`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180053986`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800539a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800539a6`

## string_xrefs

- `0x180053a26`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180053acd`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180053c0e`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180053c98`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800539f6`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180053a0e`: `onecore\com\combase\rpcss\objex\token.cxx`

## pseudocode

```c

```
