# operator delete(void *)

- ea: `0x180001f8c`
- end: `0x180001f91`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001160`
- `0x180001450`
- `0x180001590`
- `0x180001770`
- `0x180001870`
- `0x180002888`
- `0x180002a30`
- `0x180002a68`
- `0x180002a90`
- `0x180002ddc`
- `0x180003730`
- `0x180003768`
- `0x180003ef0`

## callees

- `0x180002466`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x180001f8c  jmp     free_0
```
