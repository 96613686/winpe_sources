# operator delete[](void *,unsigned __int64)

- ea: `0x1400013b4`
- end: `0x1400013b9`
- name: `??_V@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140003070`
- `0x140005ee4`

## callees

- `0x140001008`

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
0x1400013b4  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
