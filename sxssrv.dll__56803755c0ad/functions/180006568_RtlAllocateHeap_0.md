# RtlAllocateHeap_0

- ea: `0x180006568`
- end: `0x18000656e`
- name: `RtlAllocateHeap_0`
- size: `6`
- prototype: `PVOID __stdcall(PVOID HeapHandle, ULONG Flags, SIZE_T Size)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800060c0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180006568`

## pseudocode

```c
// attributes: thunk
PVOID __stdcall RtlAllocateHeap_0(PVOID HeapHandle, ULONG Flags, SIZE_T Size)
{
  return RtlAllocateHeap(HeapHandle, Flags, Size);
}

```

## disassembly

```asm
0x180006568  jmp     cs:__imp_RtlAllocateHeap
```
