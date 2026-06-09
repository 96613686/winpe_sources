# operator delete(void *,unsigned __int64)

- ea: `0x1800348e0`
- end: `0x1800348e5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800360c0`
- `0x180036100`

## callees

- `0x180034d5c`

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
0x1800348e0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
