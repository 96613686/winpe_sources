# operator delete(void *)

- ea: `0x140001fa4`
- end: `0x140001fa9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140005480`

## callees

- `0x140001fbc`

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
0x140001fa4  jmp     free_0
```
