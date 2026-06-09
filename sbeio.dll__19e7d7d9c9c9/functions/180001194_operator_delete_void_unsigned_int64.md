# operator delete(void *,unsigned __int64)

- ea: `0x180001194`
- end: `0x180001199`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `182`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001f7c`
- `0x1800022e0`
- `0x180002320`
- `0x180002360`
- `0x1800023a0`
- `0x1800023f0`
- `0x180002440`
- `0x1800024c4`
- `0x1800039f0`
- `0x180005410`
- `0x1800054e0`
- `0x180005df0`
- `0x180007bd8`
- `0x180007ee0`
- `0x180007f30`
- `0x180007f74`
- `0x180007fa0`
- `0x1800086d0`
- `0x1800088e0`
- `0x180009150`
- `0x180009820`
- `0x18000a750`
- `0x18000a860`
- `0x18000afa0`
- `0x18000bb80`
- `0x18000bc60`
- `0x18000bd30`
- `0x18000c2a0`
- `0x18000c914`
- `0x18000cd9c`
- `0x18000d67c`
- `0x18000d820`
- `0x18000d870`
- `0x18000d8b0`
- `0x18000dbb0`
- `0x18000dfe0`
- `0x18000e360`
- `0x18000e3a0`
- `0x18000e3e0`
- `0x18000e5c0`
- `0x18000ebd0`
- `0x18000f2c0`
- `0x18000f390`
- `0x18000f890`
- `0x18000fdf0`
- `0x18000fe30`
- `0x180010798`
- `0x180010870`
- `0x180011690`
- `0x1800117c0`

## callees

- `0x1800011e0`

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
0x180001194  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
