# RtlAllocateHeap_0

- ea: `0x18000663c`
- end: `0x180006642`
- name: `RtlAllocateHeap_0`
- size: `6`
- prototype: `PVOID __stdcall(PVOID HeapHandle, ULONG Flags, SIZE_T Size)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180006180`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000663c`

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
0x18000663c  jmp     cs:__imp_RtlAllocateHeap
```
