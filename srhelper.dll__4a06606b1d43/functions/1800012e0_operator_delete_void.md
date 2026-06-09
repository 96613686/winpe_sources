# operator delete[](void *)

- ea: `0x1800012e0`
- end: `0x1800012e5`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800072a8`
- `0x180007fd0`

## callees

- `0x1800012d4`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1800012e0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
