# operator delete(void *)

- ea: `0x180001fa8`
- end: `0x180001fad`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001b00`
- `0x180001b40`
- `0x180002980`
- `0x180002c20`
- `0x180002f84`
- `0x180002fb0`
- `0x180002fd8`
- `0x180004750`
- `0x180004ad4`
- `0x180006450`
- `0x180006cd8`
- `0x180009520`
- `0x18000a070`
- `0x18000a0b0`
- `0x18000a0f0`
- `0x18000a130`
- `0x18000a3b0`
- `0x18000b190`

## callees

- `0x18000249c`

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
0x180001fa8  jmp     free_0
```
