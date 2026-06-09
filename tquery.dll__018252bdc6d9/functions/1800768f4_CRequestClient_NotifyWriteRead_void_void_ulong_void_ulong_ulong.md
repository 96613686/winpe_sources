# CRequestClient::NotifyWriteRead(void *,void *,ulong,void *,ulong,ulong &)

- ea: `0x1800768f4`
- end: `0x180076b27`
- name: `?NotifyWriteRead@CRequestClient@@QEAAHPEAX0K0KAEAK@Z`
- size: `563`
- prototype: `__int64 __fastcall(CRequestClient *__hidden this, void *, void *, unsigned int, CProxyMessage *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180076830`
- `0x1801c2710`
- `0x1801c2cc0`

## callees

- `0x180038f08`
- `0x1800699a0`
- `0x180072768`
- `0x180073ea0`
- `0x180076448`
- `0x1800768f4`
- `0x180076b30`
- `0x1800eae08`
- `0x1800eb364`
- `0x180176848`
- `0x180188d90`
- `0x18018e8cb`
- `0x180294310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007695f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007695f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800769c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800769e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076942`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180076942`

## string_xrefs

- `0x180076971`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180076997`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180076a94`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180076b15`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180076a88`: `[Proxy] NotifyWriteRead complete cb %d, msg %d\n`

## pseudocode

```c

```
