# operator delete(void *)

- ea: `0x180001820`
- end: `0x180001825`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002110`
- `0x1800027d0`
- `0x180002800`
- `0x180002f90`

## callees

- `0x180001cf6`

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
0x180001820  jmp     free_0
```
