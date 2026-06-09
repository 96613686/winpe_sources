# operator delete(void *,unsigned __int64)

- ea: `0x18000e664`
- end: `0x18000e669`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ff70`
- `0x18000ffb0`
- `0x180013b40`
- `0x180013b80`
- `0x180014bd8`
- `0x180016010`
- `0x180016050`

## callees

- `0x18000ec10`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18000e664  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
