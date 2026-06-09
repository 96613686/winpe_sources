# operator delete(void *,unsigned __int64)

- ea: `0x18000c264`
- end: `0x18000c269`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000d8a0`

## callees

- `0x18000c7e0`

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
0x18000c264  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
