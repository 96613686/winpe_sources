# operator delete(void *,unsigned __int64)

- ea: `0x18000b920`
- end: `0x18000b925`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001160`
- `0x180003ea0`
- `0x180004170`
- `0x18000d6b0`
- `0x18000d6f0`
- `0x180012904`

## callees

- `0x18000bde4`

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
0x18000b920  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
