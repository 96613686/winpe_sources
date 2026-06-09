# operator delete(void *,unsigned __int64)

- ea: `0x140002714`
- end: `0x140002719`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `20`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004ca0`
- `0x140004ce0`
- `0x140004d20`
- `0x140004d60`
- `0x14000b19c`
- `0x14000d360`
- `0x14000d400`
- `0x14000d440`
- `0x14000d4b0`
- `0x14000ee80`
- `0x14000ef00`
- `0x140015e24`
- `0x140018d0c`
- `0x14001f3cc`
- `0x14001f3ec`
- `0x140021da0`
- `0x140021df0`
- `0x140025210`
- `0x140025260`
- `0x1400279e3`

## callees

- `0x140002468`

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
0x140002714  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
