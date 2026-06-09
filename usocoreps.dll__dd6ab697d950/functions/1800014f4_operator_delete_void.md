# operator delete(void *)

- ea: `0x1800014f4`
- end: `0x1800014f9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001534`
- `0x180001920`
- `0x180001f50`

## callees

- `0x1800020ee`

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
0x1800014f4  jmp     free
```
