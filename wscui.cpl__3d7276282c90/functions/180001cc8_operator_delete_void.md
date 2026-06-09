# operator delete(void *)

- ea: `0x180001cc8`
- end: `0x180001ccd`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `12`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002320`
- `0x180003250`
- `0x180003690`
- `0x1800036c8`
- `0x180004300`
- `0x180004370`
- `0x180005cf4`
- `0x180007da0`
- `0x180007dd0`
- `0x1800080f0`
- `0x18000844c`
- `0x180009590`

## callees

- `0x18000241d`

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
0x180001cc8  jmp     free_0
```
