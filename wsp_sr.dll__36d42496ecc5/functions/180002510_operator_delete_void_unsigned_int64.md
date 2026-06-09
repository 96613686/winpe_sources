# operator delete(void *,unsigned __int64)

- ea: `0x180002510`
- end: `0x180002515`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `31`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004d30`
- `0x18000570c`
- `0x180005ad0`
- `0x180005b20`
- `0x180008d30`
- `0x180008d6c`
- `0x180008db0`
- `0x180011b80`
- `0x180011bc0`
- `0x180017bf0`
- `0x180017c30`
- `0x180017c70`
- `0x180017cb0`
- `0x180017cf0`
- `0x180017d30`
- `0x180020130`
- `0x1800241b0`
- `0x180025e30`
- `0x180027f58`
- `0x180027f90`
- `0x180027fd0`
- `0x180028010`
- `0x180028050`
- `0x180028500`
- `0x180028550`
- `0x1800286b0`
- `0x180028d50`
- `0x18002ad72`
- `0x18002b6e0`
- `0x18002be52`
- `0x18002c1d9`

## callees

- `0x180002924`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002510  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
