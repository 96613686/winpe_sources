# operator delete(void *)

- ea: `0x180010c64`
- end: `0x180010c69`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180010334`
- `0x180010710`
- `0x1800135b0`

## callees

- `0x18001028c`

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
0x180010c64  jmp     free
```
