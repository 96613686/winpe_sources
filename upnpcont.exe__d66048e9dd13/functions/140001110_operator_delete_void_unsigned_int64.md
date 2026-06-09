# operator delete(void *,unsigned __int64)

- ea: `0x140001110`
- end: `0x140001115`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400020a0`
- `0x140002110`
- `0x140002160`
- `0x1400021a0`
- `0x1400021e4`
- `0x1400032c0`
- `0x140003540`
- `0x140005160`
- `0x140005294`
- `0x140005c80`

## callees

- `0x140001104`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x140001110  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
