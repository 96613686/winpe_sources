# operator delete(void *)

- ea: `0x1800027d4`
- end: `0x1800027d9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002814`
- `0x180002820`
- `0x1800031f0`
- `0x18000c0c0`
- `0x18000c0f0`
- `0x18000c940`
- `0x18000ed10`

## callees

- `0x180003384`

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
0x1800027d4  jmp     free
```
