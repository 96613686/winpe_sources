# operator delete[](void *)

- ea: `0x180016a1c`
- end: `0x180016a21`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180016084`
- `0x180016710`

## callees

- `0x180015104`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180016a1c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
