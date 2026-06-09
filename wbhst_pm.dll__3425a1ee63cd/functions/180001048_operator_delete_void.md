# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800025e0`
- `0x1800034e0`
- `0x180003700`
- `0x1800041c0`

## callees

- `0x180001526`

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
