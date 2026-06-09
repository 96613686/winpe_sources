# operator delete(void *)

- ea: `0x180002954`
- end: `0x180002959`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002540`
- `0x180002550`

## callees

- `0x180001e14`

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
0x180002954  jmp     free
```
