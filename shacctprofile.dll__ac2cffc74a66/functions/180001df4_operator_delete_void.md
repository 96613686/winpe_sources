# operator delete(void *)

- ea: `0x180001df4`
- end: `0x180001df9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002600`
- `0x180009920`

## callees

- `0x180002b5e`

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
0x180001df4  jmp     free
```
