# operator delete(void *)

- ea: `0x180001ea4`
- end: `0x180001ea9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002360`
- `0x180002370`

## callees

- `0x180002a54`

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
0x180001ea4  jmp     free
```
