# operator delete(void *)

- ea: `0x180005284`
- end: `0x180005289`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005278`
- `0x180005a50`
- `0x180013f10`
- `0x1800149ac`
- `0x1800149e0`
- `0x180014a20`
- `0x180015398`

## callees

- `0x180006004`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free(Block);
}

```

## disassembly

```asm
0x180005284  jmp     free
```
