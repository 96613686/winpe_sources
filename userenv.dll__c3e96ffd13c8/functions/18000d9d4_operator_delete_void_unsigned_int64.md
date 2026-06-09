# operator delete(void *,unsigned __int64)

- ea: `0x18000d9d4`
- end: `0x18000d9d9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f1d0`
- `0x18000f210`
- `0x180012a80`
- `0x180012ac0`
- `0x180013b24`
- `0x180014d80`
- `0x180014dc0`

## callees

- `0x18000df80`

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
0x18000d9d4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
