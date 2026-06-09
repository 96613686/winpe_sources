# operator delete(void *,unsigned __int64)

- ea: `0x180001534`
- end: `0x180001539`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002204`
- `0x180002248`
- `0x1800023e0`
- `0x180002430`
- `0x18000246c`
- `0x180002f58`

## callees

- `0x1800014f4`

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
0x180001534  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
