# operator delete(void *,unsigned __int64)

- ea: `0x180012c50`
- end: `0x180012c55`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800144e0`
- `0x180014520`
- `0x1800338d8`
- `0x1800338f4`
- `0x180033960`
- `0x1800339a0`
- `0x1800340d4`

## callees

- `0x180013134`

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
0x180012c50  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
