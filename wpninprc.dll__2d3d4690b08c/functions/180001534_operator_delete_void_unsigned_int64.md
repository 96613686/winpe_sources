# operator delete(void *,unsigned __int64)

- ea: `0x180001534`
- end: `0x180001539`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800023c0`
- `0x180002400`
- `0x180006010`
- `0x180006210`

## callees

- `0x180001b00`

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
0x180001534  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
