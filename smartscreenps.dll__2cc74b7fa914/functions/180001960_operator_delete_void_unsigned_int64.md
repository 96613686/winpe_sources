# operator delete(void *,unsigned __int64)

- ea: `0x180001960`
- end: `0x180001965`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800077c0`
- `0x180007800`
- `0x18000ac00`
- `0x18000ac50`
- `0x18000ac90`
- `0x18000b820`

## callees

- `0x1800019d0`

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
0x180001960  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
