# operator delete(void *)

- ea: `0x18000c53c`
- end: `0x18000c541`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000ce4c`
- `0x18000ce60`

## callees

- `0x18000d434`

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
0x18000c53c  jmp     free
```
