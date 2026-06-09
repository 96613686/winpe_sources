# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001930`
- `0x1800027e0`
- `0x1800027f0`
- `0x180002814`
- `0x180002d20`
- `0x180002db8`
- `0x180003818`
- `0x180003c74`
- `0x180004204`
- `0x1800045ac`
- `0x180004770`

## callees

- `0x180001526`

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
0x180001048  jmp     free_0
```
