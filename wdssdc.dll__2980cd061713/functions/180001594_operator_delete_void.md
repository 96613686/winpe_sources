# operator delete(void *)

- ea: `0x180001594`
- end: `0x180001599`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800015d4`
- `0x180002190`
- `0x180002520`

## callees

- `0x180002634`

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
0x180001594  jmp     free
```
