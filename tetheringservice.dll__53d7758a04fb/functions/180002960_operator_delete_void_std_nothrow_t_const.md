# operator delete(void *,std::nothrow_t const &)

- ea: `0x180002960`
- end: `0x180002965`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `52`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005080`
- `0x1800050c0`
- `0x180005100`
- `0x180005140`
- `0x18000d960`
- `0x18000d9c0`
- `0x18000dfd8`
- `0x18000fae4`
- `0x18000fc24`
- `0x18000fe0c`
- `0x18000feb8`
- `0x18000fedc`
- `0x180010e84`
- `0x180014a0c`
- `0x180014a74`
- `0x180014bd0`
- `0x180014c30`
- `0x18001b810`
- `0x18001dc08`
- `0x18001f670`
- `0x180020030`
- `0x180020da0`
- `0x180020e80`
- `0x180024890`
- `0x1800248c0`
- `0x180024920`
- `0x180024950`
- `0x180025174`
- `0x180027090`
- `0x1800273e0`
- `0x180028804`
- `0x180028d20`
- `0x180028d50`
- `0x180028d90`
- `0x180028e74`
- `0x180028ef8`
- `0x180029020`
- `0x1800298e0`
- `0x180029910`
- `0x180029950`
- `0x18002c7bc`
- `0x18002d868`
- `0x18002f468`
- `0x1800313e0`
- `0x180031ac4`
- `0x180031c1b`
- `0x180032225`
- `0x180032441`
- `0x18003250c`
- `0x18003252f`

## callees

- `0x180002574`

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
0x180002960  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
