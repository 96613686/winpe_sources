# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `8`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001b50`
- `0x180001b80`
- `0x180001bb0`
- `0x180001c30`
- `0x180002c28`
- `0x180002d10`
- `0x180002d40`
- `0x180002d80`

## callees

- `0x18000153c`

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
0x180001048  jmp     free_0
```
