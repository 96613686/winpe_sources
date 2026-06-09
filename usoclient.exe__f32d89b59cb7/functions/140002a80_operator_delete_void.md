# operator delete(void *)

- ea: `0x140002a80`
- end: `0x140002a85`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400023b4`
- `0x1400023c0`

## callees

- `0x140002c34`

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
0x140002a80  jmp     free
```
