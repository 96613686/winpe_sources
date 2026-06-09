# ConnectionAggregator::InternalSetInterfaceTokens(_GUID const *,int,WCM_CONNECT_TOKEN const *)

- ea: `0x18001e6b4`
- end: `0x18001e90e`
- name: `?InternalSetInterfaceTokens@ConnectionAggregator@@AEAAKPEBU_GUID@@HPEBUWCM_CONNECT_TOKEN@@@Z`
- size: `602`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, const struct _GUID *, int, const struct WCM_CONNECT_TOKEN *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000942c`

## callees

- `0x180010080`
- `0x180010ff0`
- `0x180011bb0`
- `0x180011c20`
- `0x180019434`
- `0x18001e6b4`
- `0x18001f7d0`
- `0x18001f8d8`
- `0x18006da48`
- `0x18006db98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e6f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e6f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e7aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e81a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e7aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e81a`

## string_xrefs

- `0x18001e77e`: `ConnectionAggregator::InternalSetInterfaceTokens`
- `0x18001e891`: `ConnectionAggregator::InternalSetInterfaceTokens`
- `0x18001e8b2`: `ConnectionAggregator::InternalSetInterfaceTokens`

## pseudocode

```c

```
