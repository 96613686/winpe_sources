# BaseSrvActivationContextCacheAVLTableAllocate

- ea: `0x180006390`
- end: `0x1800063a9`
- name: `BaseSrvActivationContextCacheAVLTableAllocate`
- size: `25`
- prototype: `RTL_AVL_ALLOCATE_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800063a2`

## pseudocode

```c
PVOID __fastcall BaseSrvActivationContextCacheAVLTableAllocate(struct _RTL_AVL_TABLE *Table, CLONG ByteSize)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ByteSize);
}

```

## disassembly

```asm
0x180006390  mov     rcx, gs:60h
0x180006399  mov     r8d, edx
0x18000639c  xor     edx, edx
0x18000639e  mov     rcx, [rcx+30h]
0x1800063a2  jmp     cs:__imp_RtlAllocateHeap
```
