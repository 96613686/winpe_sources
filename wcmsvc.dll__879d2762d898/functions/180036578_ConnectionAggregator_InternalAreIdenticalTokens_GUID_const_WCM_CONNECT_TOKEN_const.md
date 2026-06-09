# ConnectionAggregator::InternalAreIdenticalTokens(_GUID const *,WCM_CONNECT_TOKEN const *)

- ea: `0x180036578`
- end: `0x180036825`
- name: `?InternalAreIdenticalTokens@ConnectionAggregator@@AEAAHPEBU_GUID@@PEBUWCM_CONNECT_TOKEN@@@Z`
- size: `685`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _GUID *, const struct WCM_CONNECT_TOKEN *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800364c0`

## callees

- `0x180010080`
- `0x180010ff0`
- `0x180011bb0`
- `0x180011c20`
- `0x1800137a0`
- `0x180019434`
- `0x180036578`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800365c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800365c4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003663c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800366a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003663c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800366a6`

## string_xrefs

- `0x1800365a5`: `ConnectionAggregator::InternalAreIdenticalTokens`

## pseudocode

```c

```
