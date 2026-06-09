# operator delete(void *)

- ea: `0x180037024`
- end: `0x180037029`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180036834`
- `0x180036840`

## callees

- `0x180037144`

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
0x180037024  jmp     free
```
