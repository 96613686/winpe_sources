# operator delete(void *)

- ea: `0x180034d5c`
- end: `0x180034d61`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800348e0`

## callees

- `0x180034e54`

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
0x180034d5c  jmp     free
```
