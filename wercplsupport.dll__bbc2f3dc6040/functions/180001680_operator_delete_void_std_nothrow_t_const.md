# operator delete(void *,std::nothrow_t const &)

- ea: `0x180001680`
- end: `0x180001685`
- name: `??3@YAXPEAXAEBUnothrow_t@std@@@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002ad0`
- `0x180004970`
- `0x180004d28`
- `0x18000531c`
- `0x18000576c`
- `0x180005c28`
- `0x180005e04`
- `0x1800066a8`
- `0x180006754`
- `0x1800068cc`

## callees

- `0x180001674`

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
0x180001680  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
