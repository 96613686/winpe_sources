# operator delete(void *)

- ea: `0x1800031f4`
- end: `0x1800031f9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `17`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001010`
- `0x180001b30`
- `0x180001fd0`
- `0x180004410`
- `0x1800058d0`
- `0x180005f00`
- `0x180006df0`
- `0x180008140`
- `0x180008178`
- `0x180008a04`
- `0x180008ea4`
- `0x180009078`
- `0x1800091fc`
- `0x1800093c0`
- `0x18000a180`
- `0x18000a460`
- `0x18000a848`

## callees

- `0x180003706`

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
0x1800031f4  jmp     free_0
```
