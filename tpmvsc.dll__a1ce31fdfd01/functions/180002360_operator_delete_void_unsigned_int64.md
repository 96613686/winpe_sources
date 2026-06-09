# operator delete(void *,unsigned __int64)

- ea: `0x180002360`
- end: `0x180002365`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003840`
- `0x180003880`
- `0x180006238`
- `0x18000dc38`
- `0x18000f374`
- `0x18000f3a4`
- `0x18000f440`
- `0x18000f47c`
- `0x18000f4c0`
- `0x18000f500`
- `0x180015ca8`
- `0x18001b420`
- `0x18001c0bc`
- `0x180025fb0`
- `0x180025ff0`
- `0x18002602c`
- `0x180027e54`
- `0x180027e80`
- `0x18003599c`
- `0x180035b21`
- `0x180035c74`
- `0x1800366fa`

## callees

- `0x180001ea4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002360  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
