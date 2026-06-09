# SetStringIter::CreatePath(Unattend &,SetStringIter::ModifyContext,ushort const *,ushort const *,SetStringIter::ModifyContext &)

- ea: `0x180043efc`
- end: `0x1800443f3`
- name: `?CreatePath@SetStringIter@@QEAAJAEAVUnattend@@UModifyContext@1@PEBG2AEAU31@@Z`
- size: `1271`
- prototype: `int __high(struct Unattend *, struct SetStringIter::ModifyContext, const unsigned __int16 *, const unsigned __int16 *, struct SetStringIter::ModifyContext *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x180044400`

## callees

- `0x180010508`
- `0x180041a74`
- `0x180041c8c`
- `0x180041d98`
- `0x180041dc0`
- `0x180041e5c`
- `0x180043764`
- `0x180043efc`
- `0x180048734`
- `0x1800488ec`
- `0x180048f9c`
- `0x1800607b0`
- `0x180060ce2`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004414d`
- `KERNEL32!HeapFree` at `0x180044287`
- `KERNEL32!HeapFree` at `0x1800442fc`
- `KERNEL32!HeapFree` at `0x18004433f`
- `KERNEL32!HeapFree` at `0x18004414d`
- `KERNEL32!HeapFree` at `0x180044287`
- `KERNEL32!HeapFree` at `0x1800442fc`
- `KERNEL32!HeapFree` at `0x18004433f`
- `KERNEL32!GetProcessHeap` at `0x180044139`
- `KERNEL32!GetProcessHeap` at `0x180044273`
- `KERNEL32!GetProcessHeap` at `0x1800442e8`
- `KERNEL32!GetProcessHeap` at `0x18004432b`
- `KERNEL32!GetProcessHeap` at `0x180044139`
- `KERNEL32!GetProcessHeap` at `0x180044273`
- `KERNEL32!GetProcessHeap` at `0x1800442e8`
- `KERNEL32!GetProcessHeap` at `0x18004432b`
- `ntdll!RtlAllocateHeap` at `0x18004403e`
- `ntdll!RtlAllocateHeap` at `0x180044104`
- `ntdll!RtlAllocateHeap` at `0x180044221`
- `ntdll!RtlAllocateHeap` at `0x18004403e`
- `ntdll!RtlAllocateHeap` at `0x180044104`
- `ntdll!RtlAllocateHeap` at `0x180044221`
- `ntdll!RtlNtStatusToDosError` at `0x1800442c0`
- `ntdll!RtlNtStatusToDosError` at `0x1800443b7`
- `ntdll!RtlNtStatusToDosError` at `0x1800442c0`
- `ntdll!RtlNtStatusToDosError` at `0x1800443b7`

## pseudocode

```c

```
