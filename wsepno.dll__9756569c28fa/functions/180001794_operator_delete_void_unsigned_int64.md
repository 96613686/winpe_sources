# operator delete(void *,unsigned __int64)

- ea: `0x180001794`
- end: `0x180001799`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002570`
- `0x1800025b0`
- `0x180004ca0`
- `0x180005400`
- `0x180005440`
- `0x180005480`
- `0x1800054c0`
- `0x180005510`
- `0x180005550`
- `0x180006040`
- `0x1800068e0`
- `0x180006b50`
- `0x1800077f0`
- `0x18000a0a0`
- `0x18000c0b0`
- `0x18000c694`
- `0x18000c6fc`

## callees

- `0x180001754`

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
0x180001794  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
