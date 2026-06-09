# operator delete(void *)

- ea: `0x1800135cc`
- end: `0x1800135d1`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001770`
- `0x180013544`
- `0x180014790`
- `0x180015434`
- `0x180015d90`

## callees

- `0x180013aa6`

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
0x1800135cc  jmp     free_0
```
