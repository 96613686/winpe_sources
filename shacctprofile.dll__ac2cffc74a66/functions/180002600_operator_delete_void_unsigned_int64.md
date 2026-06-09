# operator delete(void *,unsigned __int64)

- ea: `0x180002600`
- end: `0x180002605`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005f20`
- `0x180006060`
- `0x180006180`
- `0x180006c30`
- `0x180006c70`
- `0x18000731c`

## callees

- `0x180001df4`

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
0x180002600  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
