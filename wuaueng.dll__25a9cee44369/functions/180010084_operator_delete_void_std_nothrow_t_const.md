# operator delete(void *,std::nothrow_t const &)

- ea: `0x180010084`
- end: `0x180010089`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __fastcall(void *, const struct std::nothrow_t *)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001dc0`
- `0x180002ea0`
- `0x180006270`
- `0x180006480`
- `0x180006a30`
- `0x180006cec`
- `0x180006f20`
- `0x1800073dc`
- `0x180007574`
- `0x1800076c4`
- `0x1800077f8`
- `0x180007d10`
- `0x180007ee8`
- `0x180007ff0`
- `0x180008f84`
- `0x1800093b8`
- `0x1800094f8`
- `0x18000a270`
- `0x18000a2b0`
- `0x18000a574`
- `0x18000a85c`
- `0x18000a98c`
- `0x18001681b`

## callees

- `0x180010a98`

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
0x180010084  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
