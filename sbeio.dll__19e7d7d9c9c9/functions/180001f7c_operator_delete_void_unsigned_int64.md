# operator delete[](void *,unsigned __int64)

- ea: `0x180001f7c`
- end: `0x180001f81`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180015a9c`
- `0x180015f70`
- `0x1800168e0`
- `0x180016960`
- `0x180021130`
- `0x180022b30`
- `0x180024ad4`

## callees

- `0x180001194`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180001f7c  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
