# HcsClient::OperationTracker::CompletePendingOperationsOnExitEvent(_GUID const &,long,ushort const *)

- ea: `0x18003d8c4`
- end: `0x18003dc12`
- name: `?CompletePendingOperationsOnExitEvent@OperationTracker@HcsClient@@AEAAXAEBU_GUID@@JPEBG@Z`
- size: `846`
- prototype: `void(HcsClient::OperationTracker *__hidden this, const struct _GUID *, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18003c694`

## callees

- `0x180002f50`
- `0x180003c78`
- `0x1800171ac`
- `0x180017980`
- `0x18001a014`
- `0x1800212c4`
- `0x180037f54`
- `0x18003b730`
- `0x18003c058`
- `0x18003d3b4`
- `0x18003d8c4`
- `0x18003ecc8`
- `0x180040720`
- `0x180040760`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d955`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d955`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003da84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003da84`

## string_xrefs

- `0x18003d913`: `ClientLib_CompleteAllOperations`

## pseudocode

```c

```
