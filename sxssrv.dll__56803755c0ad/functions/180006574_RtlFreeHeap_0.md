# RtlFreeHeap_0

- ea: `0x180006574`
- end: `0x18000657a`
- name: `RtlFreeHeap_0`
- size: `6`
- prototype: `BOOLEAN __stdcall(HANDLE HeapHandle, ULONG Flags, PVOID P)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800060c0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006574`

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
0x180006574  jmp     cs:__imp_RtlFreeHeap
```
