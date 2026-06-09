# BaseSrvActivationContextCacheAVLTableFree

- ea: `0x180006740`
- end: `0x180006759`
- name: `BaseSrvActivationContextCacheAVLTableFree`
- size: `25`
- prototype: `void __fastcall(struct _RTL_AVL_TABLE *Table, PVOID Buffer)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180006752`

## pseudocode

```c
void __fastcall BaseSrvActivationContextCacheAVLTableFree(struct _RTL_AVL_TABLE *Table, PVOID Buffer)
{
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
}

```

## disassembly

```asm
0x180006740  mov     rcx, gs:60h
0x180006749  mov     r8, rdx
0x18000674c  xor     edx, edx
0x18000674e  mov     rcx, [rcx+30h]
0x180006752  jmp     cs:__imp_RtlFreeHeap
```
