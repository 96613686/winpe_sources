# operator delete(void *,unsigned __int64)

- ea: `0x180001494`
- end: `0x180001499`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001f38`
- `0x18000200c`
- `0x180002a70`
- `0x180002b40`
- `0x180004270`
- `0x1800042e0`
- `0x180004424`

## callees

- `0x1800019b0`

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
0x180001494  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
