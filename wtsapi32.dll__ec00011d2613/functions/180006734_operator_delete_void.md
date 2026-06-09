# operator delete(void *)

- ea: `0x180006734`
- end: `0x180006739`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `24`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180006de0`
- `0x180007ab0`
- `0x18000befc`
- `0x18000c0c0`
- `0x18000c270`
- `0x18000f100`
- `0x18000f130`
- `0x18000f170`
- `0x18000f1b0`
- `0x18000f1f8`
- `0x18000fec0`
- `0x180011310`
- `0x1800125a0`
- `0x1800125d0`
- `0x180012608`
- `0x180012690`
- `0x180012c20`
- `0x1800133f0`
- `0x180013d30`
- `0x180014390`
- `0x1800144a4`
- `0x180014698`
- `0x180014898`
- `0x180015050`

## callees

- `0x180006deb`

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
0x180006734  jmp     free_0
```
