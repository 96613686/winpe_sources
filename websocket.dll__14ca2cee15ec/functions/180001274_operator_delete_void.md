# operator delete(void *)

- ea: `0x180001274`
- end: `0x180001279`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001750`
- `0x180003cf8`
- `0x180003e20`
- `0x1800045c0`
- `0x180005cb0`
- `0x180009350`
- `0x1800093c4`
- `0x18000992c`
- `0x18000a3c4`
- `0x18000a438`
- `0x18000a8a0`
- `0x18000aa84`
- `0x18000af30`
- `0x18000b0c8`
- `0x18000b194`
- `0x18000b438`
- `0x18000b4f4`
- `0x18000ba64`
- `0x18000c7c0`
- `0x18000caf0`
- `0x18000cbc0`
- `0x18000da74`

## callees

- `0x180001f74`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180001274  jmp     free
```
