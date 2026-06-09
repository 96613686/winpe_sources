# operator delete(void *)

- ea: `0x180001b00`
- end: `0x180001b05`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001534`
- `0x180001540`
- `0x180001f00`

## callees

- `0x18000206e`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180001b00  jmp     free
```
