# operator delete(void *)

- ea: `0x18000f704`
- end: `0x18000f709`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ed64`
- `0x18000ed70`
- `0x1800134a0`

## callees

- `0x18000ed00`

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
0x18000f704  jmp     free
```
