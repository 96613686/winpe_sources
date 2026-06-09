# operator delete(void *,unsigned __int64)

- ea: `0x180002aa0`
- end: `0x180002aa5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003ef0`
- `0x180003f30`
- `0x1800076e4`
- `0x1800077dc`
- `0x180007930`
- `0x180007a34`
- `0x180007b50`
- `0x180007cc4`
- `0x180007dfc`
- `0x180007f3c`
- `0x1800081ec`
- `0x180008aa0`
- `0x180008b08`
- `0x180009190`
- `0x1800091d0`
- `0x180009210`
- `0x180009280`
- `0x1800092b0`
- `0x180009300`
- `0x180009e38`
- `0x18000b260`
- `0x18000b2a0`
- `0x18000b300`
- `0x18000e7c0`

## callees

- `0x18000302c`

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
0x180002aa0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
