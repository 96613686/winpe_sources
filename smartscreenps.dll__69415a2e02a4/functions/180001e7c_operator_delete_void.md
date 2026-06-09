# operator delete(void *)

- ea: `0x180001e7c`
- end: `0x180001e81`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001960`
- `0x180001990`
- `0x180001fd0`

## callees

- `0x18000691a`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001e7c  jmp     free_0
```
