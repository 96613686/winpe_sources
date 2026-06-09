# operator delete(void *,std::nothrow_t const &)

- ea: `0x180006de0`
- end: `0x180006de5`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800063c8`
- `0x180006604`
- `0x18000beb4`
- `0x180015a10`

## callees

- `0x180006734`

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
0x180006de0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
