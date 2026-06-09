# operator delete(void *,unsigned __int64)

- ea: `0x180001960`
- end: `0x180001965`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007790`
- `0x1800077d0`
- `0x18000ab0c`
- `0x18000ae90`
- `0x18000aee0`
- `0x18000af20`
- `0x18000baf0`

## callees

- `0x180001e7c`

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
