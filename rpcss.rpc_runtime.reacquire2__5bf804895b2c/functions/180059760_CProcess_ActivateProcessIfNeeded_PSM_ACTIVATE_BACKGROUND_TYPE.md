# CProcess::ActivateProcessIfNeeded(_PSM_ACTIVATE_BACKGROUND_TYPE)

- ea: `0x180059760`
- end: `0x180059b26`
- name: `?ActivateProcessIfNeeded@CProcess@@QEAAJW4_PSM_ACTIVATE_BACKGROUND_TYPE@@@Z`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009054`

## callees

- `0x18000b398`
- `0x18001ecf0`
- `0x18001f018`
- `0x1800210f8`
- `0x18002f5a0`
- `0x18002f670`
- `0x180034260`
- `0x180059760`
- `0x18006016c`
- `0x180060b04`
- `0x180060bbc`
- `0x18008172c`
- `0x180095c0c`

## import_xrefs

- `ntdll!NtSetSystemInformation` at `0x180059a01`
- `ntdll!NtSetSystemInformation` at `0x180059a01`
- `ntdll!NtQueryInformationProcess` at `0x18005993e`
- `ntdll!NtQueryInformationProcess` at `0x18005993e`
- `ntdll!RtlNtStatusToDosError` at `0x180059ada`
- `ntdll!RtlNtStatusToDosError` at `0x180059ada`
- `RPCRT4!NdrClientCall2` at `0x180059990`
- `RPCRT4!NdrClientCall2` at `0x180059990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059a11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180059a11`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059796`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059796`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800597bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800597bc`

## string_xrefs

- `0x180059842`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x1800598e9`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180059a42`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180059acc`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180059812`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x18005982a`: `onecore\com\combase\rpcss\objex\token.cxx`

## pseudocode

```c

```
