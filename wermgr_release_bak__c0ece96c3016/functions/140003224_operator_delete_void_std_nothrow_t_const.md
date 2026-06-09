# operator delete(void *,std::nothrow_t const &)

- ea: `0x140003224`
- end: `0x140003229`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `53`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140004398`
- `0x1400044a8`
- `0x1400047bc`
- `0x1400048c8`
- `0x1400048f0`
- `0x140004a14`
- `0x140004af8`
- `0x140004b90`
- `0x140004d70`
- `0x140004e18`
- `0x1400058ec`
- `0x140006d34`
- `0x14000705c`
- `0x140008220`
- `0x14000964c`
- `0x140009da0`
- `0x14000a804`
- `0x14000b354`
- `0x14000b70c`
- `0x14000be08`
- `0x14000c488`
- `0x14000c798`
- `0x14000d0e4`
- `0x14000d87c`
- `0x14000d968`
- `0x14000db44`
- `0x14000dd88`
- `0x14000e098`
- `0x14000e49c`
- `0x140010670`
- `0x1400106b0`
- `0x1400106f0`
- `0x140010730`
- `0x1400151c8`
- `0x1400151ec`
- `0x140015604`
- `0x1400172a0`
- `0x140017300`
- `0x140017c8c`
- `0x14001852c`
- `0x1400189c4`
- `0x140018c4c`
- `0x140018d70`
- `0x1400192b0`
- `0x140019c58`
- `0x140019e3c`
- `0x14001a1bc`
- `0x14001a21c`
- `0x14001a380`
- `0x14001a420`

## callees

- `0x1400033bc`

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
0x140003224  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
