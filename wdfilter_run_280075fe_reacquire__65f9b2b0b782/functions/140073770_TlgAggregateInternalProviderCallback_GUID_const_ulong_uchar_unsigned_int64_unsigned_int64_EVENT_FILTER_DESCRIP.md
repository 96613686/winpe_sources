# TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)

- ea: `0x140073770`
- end: `0x14007381e`
- name: `?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z`
- size: `174`
- prototype: `void __fastcall(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x140007690`
- `0x1400077f0`
- `0x1400711f8`
- `0x140073770`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007380b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007380b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400737ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400737ff`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400737b3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400737b3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140073788`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140073788`

## pseudocode

```c

```
