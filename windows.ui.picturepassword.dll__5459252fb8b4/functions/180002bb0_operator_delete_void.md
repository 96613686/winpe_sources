# operator delete(void *)

- ea: `0x180002bb0`
- end: `0x180002bb5`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `33`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002634`
- `0x180004190`
- `0x180004250`
- `0x180005a48`
- `0x180005ec0`
- `0x180005ef0`
- `0x180005f30`
- `0x180005f70`
- `0x180005fb0`
- `0x18000b7d8`
- `0x18000bc00`
- `0x18000bc40`
- `0x18000bc80`
- `0x18000d0d4`
- `0x18000d22c`
- `0x18000d710`
- `0x18000d750`
- `0x18000d790`
- `0x18000d870`
- `0x18000d8c0`
- `0x18000d900`
- `0x18000d940`
- `0x18000d980`
- `0x18000d9c0`
- `0x18000da00`
- `0x18000da40`
- `0x18000da80`
- `0x180010c90`
- `0x1800153a0`
- `0x180018360`
- `0x180018840`
- `0x180019930`
- `0x18001af70`

## callees

- `0x180002f4c`

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
0x180002bb0  jmp     free
```
