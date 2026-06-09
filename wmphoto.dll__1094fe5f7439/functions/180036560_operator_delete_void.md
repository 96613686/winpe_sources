# operator delete(void *)

- ea: `0x180036560`
- end: `0x180036565`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180036264`
- `0x180036270`

## callees

- `0x180036b74`

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
0x180036560  jmp     free
```
