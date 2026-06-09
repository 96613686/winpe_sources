# operator delete(void *)

- ea: `0x14001b758`
- end: `0x14001b75d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001acf4`
- `0x14001ad00`
- `0x14001f040`

## callees

- `0x14001aa0c`

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
0x14001b758  jmp     free
```
