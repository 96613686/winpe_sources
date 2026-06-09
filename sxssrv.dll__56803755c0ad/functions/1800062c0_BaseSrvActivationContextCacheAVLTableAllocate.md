# BaseSrvActivationContextCacheAVLTableAllocate

- ea: `0x1800062c0`
- end: `0x1800062d9`
- name: `BaseSrvActivationContextCacheAVLTableAllocate`
- size: `25`
- prototype: `PVOID __fastcall(struct _RTL_AVL_TABLE *Table, CLONG ByteSize)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800062d2`

## pseudocode

```c
PVOID __fastcall BaseSrvActivationContextCacheAVLTableAllocate(struct _RTL_AVL_TABLE *Table, CLONG ByteSize)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ByteSize);
}

```

## disassembly

```asm
0x1800062c0  mov     rcx, gs:60h
0x1800062c9  mov     r8d, edx
0x1800062cc  xor     edx, edx
0x1800062ce  mov     rcx, [rcx+30h]
0x1800062d2  jmp     cs:__imp_RtlAllocateHeap
```
