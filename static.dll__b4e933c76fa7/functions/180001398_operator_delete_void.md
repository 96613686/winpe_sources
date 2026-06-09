# operator delete(void *)

- ea: `0x180001398`
- end: `0x18000139d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001010`
- `0x180001cf0`
- `0x180002bd0`
- `0x180002c04`
- `0x180002db0`
- `0x180004480`
- `0x1800044c0`
- `0x180004528`
- `0x1800053e4`
- `0x180005410`
- `0x1800058a0`

## callees

- `0x180001876`

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
0x180001398  jmp     free_0
```
