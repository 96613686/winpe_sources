# operator delete(void *,unsigned __int64)

- ea: `0x140001008`
- end: `0x14000100d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `21`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400013b4`
- `0x140002014`
- `0x14000310c`
- `0x1400039b0`
- `0x140004360`
- `0x1400079c0`
- `0x140007a40`
- `0x140007ab0`
- `0x140007b20`
- `0x140007ba0`
- `0x140009710`
- `0x140009c24`
- `0x140009d70`
- `0x14000ac24`
- `0x14000ad2c`
- `0x14000ae30`
- `0x14000c550`
- `0x14000c630`
- `0x14000c700`
- `0x14000ccb8`
- `0x14000db3c`

## callees

- `0x140001060`

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
0x140001008  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
