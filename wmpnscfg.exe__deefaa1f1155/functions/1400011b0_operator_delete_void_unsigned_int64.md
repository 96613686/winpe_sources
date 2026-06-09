# operator delete(void *,unsigned __int64)

- ea: `0x1400011b0`
- end: `0x1400011b5`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400021b8`
- `0x1400024c0`
- `0x140002510`
- `0x140002560`
- `0x14000259c`
- `0x14000302c`
- `0x140004aac`
- `0x140004c18`
- `0x140006d40`

## callees

- `0x140001164`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x1400011b0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
