# operator delete(void *,unsigned __int64)

- ea: `0x180001750`
- end: `0x180001755`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800022f0`
- `0x1800045c0`

## callees

- `0x180001274`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001750  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
