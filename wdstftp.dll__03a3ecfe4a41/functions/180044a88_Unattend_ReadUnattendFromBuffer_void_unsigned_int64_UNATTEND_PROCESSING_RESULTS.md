# Unattend::ReadUnattendFromBuffer(void *,unsigned __int64,_UNATTEND_PROCESSING_RESULTS *)

- ea: `0x180044a88`
- end: `0x180044bf8`
- name: `?ReadUnattendFromBuffer@Unattend@@QEAAJPEAX_KPEAU_UNATTEND_PROCESSING_RESULTS@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(Unattend *__hidden this, void *, unsigned __int64, struct _UNATTEND_PROCESSING_RESULTS *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180016178`
- `0x180040da0`

## callees

- `0x180044a88`
- `0x18004f950`
- `0x1800607b0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180044bcb`
- `KERNEL32!HeapFree` at `0x180044bcb`
- `KERNEL32!GetProcessHeap` at `0x180044bb6`
- `KERNEL32!GetProcessHeap` at `0x180044bb6`
- `ntdll!RtlNtStatusToDosError` at `0x180044b92`
- `ntdll!RtlNtStatusToDosError` at `0x180044b92`

## pseudocode

```c

```
