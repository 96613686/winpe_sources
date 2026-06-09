# operator delete(void *)

- ea: `0x180013134`
- end: `0x180013139`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012c50`
- `0x1800139e0`
- `0x180013b50`

## callees

- `0x1800132d4`

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
0x180013134  jmp     free
```
