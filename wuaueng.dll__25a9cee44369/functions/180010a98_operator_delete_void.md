# operator delete(void *)

- ea: `0x180010a98`
- end: `0x180010a9d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180010084`
- `0x180010090`
- `0x1800143e0`

## callees

- `0x18000fc40`

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
0x180010a98  jmp     free
```
