# operator delete(void *,unsigned __int64)

- ea: `0x18000ce4c`
- end: `0x18000ce51`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000c9b4`
- `0x180016910`
- `0x180016950`
- `0x180016990`
- `0x1800169d0`
- `0x180016a10`
- `0x180016a50`
- `0x180016ab4`
- `0x1800188d0`

## callees

- `0x18000c53c`

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
0x18000ce4c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
