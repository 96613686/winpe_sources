# operator delete(void *)

- ea: `0x140001164`
- end: `0x140001169`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400011b0`
- `0x140005e60`
- `0x140005e90`

## callees

- `0x140001e76`

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
0x140001164  jmp     free
```
