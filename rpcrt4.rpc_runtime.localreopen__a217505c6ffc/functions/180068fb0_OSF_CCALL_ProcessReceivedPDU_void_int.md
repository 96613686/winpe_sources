# OSF_CCALL::ProcessReceivedPDU(void *,int)

- ea: `0x180068fb0`
- end: `0x180069088`
- name: `?ProcessReceivedPDU@OSF_CCALL@@AEAAHPEAXH@Z`
- size: `216`
- prototype: `__int64 __fastcall(OSF_CCALL *__hidden this, struct rpcconn_common *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180068c14`

## callees

- `0x18005f9cc`
- `0x1800688d8`
- `0x180068fb0`
- `0x1800ceca9`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180069055`
- `ntdll!RtlLeaveCriticalSection` at `0x180069055`
- `ntdll!RtlEnterCriticalSection` at `0x18006903f`
- `ntdll!RtlEnterCriticalSection` at `0x18006903f`

## pseudocode

```c

```
