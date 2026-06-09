# operator delete(void *,unsigned __int64)

- ea: `0x1800022a4`
- end: `0x1800022a9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004150`
- `0x1800041b8`
- `0x1800049b0`
- `0x180004a30`
- `0x180004a70`
- `0x180004ab0`
- `0x180004af0`
- `0x180004b30`
- `0x18000e22c`
- `0x18000e47c`
- `0x18000e5bc`
- `0x18000ff64`
- `0x18001003c`
- `0x180010464`
- `0x180010500`
- `0x180010540`
- `0x1800105a0`
- `0x180014030`
- `0x180014a10`
- `0x180014a80`
- `0x180014ac0`
- `0x180019320`
- `0x18001969c`
- `0x18001a769`

## callees

- `0x180001e24`

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
0x1800022a4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
