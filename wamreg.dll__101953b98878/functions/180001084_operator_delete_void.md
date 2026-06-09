# operator delete(void *)

- ea: `0x180001084`
- end: `0x180001089`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ac0`
- `0x180001ce0`
- `0x180001ed0`
- `0x1800021d0`
- `0x180002460`
- `0x180002730`
- `0x1800029e0`
- `0x1800030b0`
- `0x1800034b0`
- `0x18000368c`
- `0x180003720`
- `0x180003b30`
- `0x180003ca0`
- `0x180003d80`
- `0x1800047a0`
- `0x1800053d8`
- `0x180005f74`

## callees

- `0x180001819`

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
0x180001084  jmp     free_0
```
