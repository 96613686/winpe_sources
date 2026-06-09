# operator delete(void *)

- ea: `0x180006124`
- end: `0x180006129`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `32`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ed0`
- `0x180002150`
- `0x1800031a0`
- `0x18000419c`
- `0x1800042f4`
- `0x180006d30`
- `0x180007200`
- `0x180007b30`
- `0x180008080`
- `0x180008930`
- `0x180009354`
- `0x180009cf0`
- `0x18000b100`
- `0x18000b158`
- `0x18000b2f8`
- `0x18000b50c`
- `0x18000b95c`
- `0x18000c00c`
- `0x18000c128`
- `0x18000c2f8`
- `0x18000c3ec`
- `0x18000c798`
- `0x18000c8b8`
- `0x18000ce3c`
- `0x18000d6a0`
- `0x18000d770`
- `0x18000d8f0`
- `0x18000dcc0`
- `0x18000dde0`
- `0x18000e150`
- `0x18000e440`
- `0x18000e5b4`

## callees

- `0x18000692c`

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
0x180006124  jmp     free_0
```
