# operator delete(void *)

- ea: `0x1800020c4`
- end: `0x1800020c9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002110`
- `0x18000213c`

## callees

- `0x180002b14`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x1800020c4  jmp     free
```
