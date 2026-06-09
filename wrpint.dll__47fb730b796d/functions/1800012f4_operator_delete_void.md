# operator delete(void *)

- ea: `0x1800012f4`
- end: `0x1800012f9`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `10`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001de0`
- `0x180002880`
- `0x1800028b0`
- `0x180002930`
- `0x180002a50`
- `0x180004bfc`
- `0x180005260`
- `0x1800056a0`
- `0x1800062d0`
- `0x180006310`

## callees

- `0x1800018d5`

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
0x1800012f4  jmp     free_0
```
