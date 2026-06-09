# BaseSrvActivationContextCacheAVLTableFree

- ea: `0x180006810`
- end: `0x180006829`
- name: `BaseSrvActivationContextCacheAVLTableFree`
- size: `25`
- prototype: `RTL_AVL_FREE_ROUTINE`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006822`

## pseudocode

```c
void __fastcall BaseSrvActivationContextCacheAVLTableFree(struct _RTL_AVL_TABLE *Table, PVOID Buffer)
{
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
}

```

## disassembly

```asm
0x180006810  mov     rcx, gs:60h
0x180006819  mov     r8, rdx
0x18000681c  xor     edx, edx
0x18000681e  mov     rcx, [rcx+30h]
0x180006822  jmp     cs:__imp_RtlFreeHeap
```
