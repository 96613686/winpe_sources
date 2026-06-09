# operator delete(void *,std::nothrow_t const &)

- ea: `0x180008ab4`
- end: `0x180008ab9`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800099c0`
- `0x180009a00`
- `0x18000ae80`
- `0x18000b030`
- `0x18000c330`
- `0x18000c370`
- `0x18000c3b0`
- `0x18000c3f0`
- `0x180014860`
- `0x180015050`
- `0x180016510`
- `0x180017c70`
- `0x1800186d0`
- `0x1800198e0`
- `0x180019920`
- `0x180019960`
- `0x18001b270`
- `0x18001b5a0`
- `0x18001d3e4`

## callees

- `0x180008a74`

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
0x180008ab4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
