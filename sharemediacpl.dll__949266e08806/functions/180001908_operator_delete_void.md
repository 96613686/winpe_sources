# operator delete(void *)

- ea: `0x180001908`
- end: `0x18000190d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001954`
- `0x180017210`
- `0x1800188c0`
- `0x180019bc0`
- `0x180019c00`
- `0x180019c60`

## callees

- `0x1800028ee`

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
0x180001908  jmp     free
```
