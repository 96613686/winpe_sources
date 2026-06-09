# RtlFreeHeap_0

- ea: `0x180006648`
- end: `0x18000664e`
- name: `RtlFreeHeap_0`
- size: `6`
- prototype: `BOOLEAN __stdcall(HANDLE HeapHandle, ULONG Flags, PVOID P)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006180`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006648`

## pseudocode

```c
// attributes: thunk
BOOLEAN __stdcall RtlFreeHeap_0(HANDLE HeapHandle, ULONG Flags, PVOID P)
{
  return RtlFreeHeap(HeapHandle, Flags, P);
}

```

## disassembly

```asm
0x180006648  jmp     cs:__imp_RtlFreeHeap
```
