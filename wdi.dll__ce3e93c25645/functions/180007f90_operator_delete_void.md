# operator delete(void *)

- ea: `0x180007f90`
- end: `0x180007f95`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800039b0`
- `0x1800039f0`

## callees

- `0x18000847e`

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
0x180007f90  jmp     free_0
```
