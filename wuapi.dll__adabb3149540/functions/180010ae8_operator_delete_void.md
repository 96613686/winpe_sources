# operator delete(void *)

- ea: `0x180010ae8`
- end: `0x180010aed`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800100d4`
- `0x1800100e0`
- `0x180014430`

## callees

- `0x18000fc90`

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
0x180010ae8  jmp     free
```
