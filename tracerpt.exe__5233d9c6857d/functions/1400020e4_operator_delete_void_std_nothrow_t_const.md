# operator delete(void *,std::nothrow_t const &)

- ea: `0x1400020e4`
- end: `0x1400020e9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `26`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000bc10`
- `0x14000c298`
- `0x140016920`
- `0x140016998`
- `0x140016ae0`
- `0x140017398`
- `0x14001d3e4`
- `0x14001db34`
- `0x14001e42c`
- `0x140021ff4`
- `0x140028130`
- `0x14002d854`
- `0x14002e544`
- `0x1400387a4`
- `0x140038850`
- `0x140038924`
- `0x140038c18`
- `0x1400397ac`
- `0x14003a0cc`
- `0x14003a6e4`
- `0x14003aab0`
- `0x14003dd0c`
- `0x14003e3a0`
- `0x140040300`
- `0x140040330`
- `0x140040360`

## callees

- `0x1400020f0`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block, const struct std::nothrow_t *a2)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1400020e4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
