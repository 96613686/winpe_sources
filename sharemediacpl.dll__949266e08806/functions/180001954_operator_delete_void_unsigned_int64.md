# operator delete(void *,unsigned __int64)

- ea: `0x180001954`
- end: `0x180001959`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800041a0`
- `0x1800041e0`
- `0x180004220`
- `0x1800061a0`
- `0x180008170`
- `0x1800081b0`
- `0x1800081f0`
- `0x18000d000`
- `0x18000d0b0`
- `0x180012f50`
- `0x180012fc0`
- `0x180014130`
- `0x1800144c4`
- `0x1800147f0`
- `0x180014a14`
- `0x180014aec`
- `0x1800154d4`
- `0x180015dd8`
- `0x180016e60`
- `0x18001cef0`

## callees

- `0x180001908`

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
0x180001954  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
