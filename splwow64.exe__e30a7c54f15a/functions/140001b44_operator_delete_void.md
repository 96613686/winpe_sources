# operator delete(void *)

- ea: `0x140001b44`
- end: `0x140001b49`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001b90`
- `0x140014080`
- `0x1400148a0`

## callees

- `0x140002864`

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
0x140001b44  jmp     free
```
