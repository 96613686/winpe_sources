# operator delete[](void *)

- ea: `0x1800012cc`
- end: `0x1800012d1`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003814`
- `0x180004220`

## callees

- `0x1800012c0`

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
0x1800012cc  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
