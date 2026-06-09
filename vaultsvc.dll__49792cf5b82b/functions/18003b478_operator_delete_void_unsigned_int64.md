# operator delete(void *,unsigned __int64)

- ea: `0x18003b478`
- end: `0x18003b47d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `21`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180009020`
- `0x180009c90`
- `0x18001ffb0`
- `0x1800280b0`
- `0x1800283d0`
- `0x180031970`
- `0x180033e60`
- `0x1800354c0`
- `0x180037b0c`
- `0x18003ba30`
- `0x18003ba70`
- `0x18003bc80`
- `0x18003be90`
- `0x18003dae0`
- `0x18003db20`
- `0x180041380`
- `0x180042ff0`
- `0x180043040`
- `0x180043080`
- `0x1800430c0`
- `0x18004b260`

## callees

- `0x18003b524`

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
0x18003b478  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
