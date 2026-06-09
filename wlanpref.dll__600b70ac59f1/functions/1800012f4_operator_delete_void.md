# operator delete[](void *)

- ea: `0x1800012f4`
- end: `0x1800012f9`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `19`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002cf0`
- `0x1800036ac`
- `0x180003fec`
- `0x1800056e0`
- `0x180005754`
- `0x18000b810`
- `0x18000b85c`
- `0x180012a70`
- `0x180013088`
- `0x180013214`
- `0x180020a10`
- `0x180027f3c`
- `0x180028064`
- `0x1800293e8`
- `0x180029510`
- `0x1800295ac`
- `0x18002bcd8`
- `0x18002bf24`
- `0x18002dde6`

## callees

- `0x1800012e8`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1800012f4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
