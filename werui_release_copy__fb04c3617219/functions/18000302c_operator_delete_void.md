# operator delete(void *)

- ea: `0x18000302c`
- end: `0x180003031`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003038`
- `0x180003070`
- `0x180004c10`
- `0x180005f80`
- `0x180005fc0`
- `0x18000b000`
- `0x18000b82c`
- `0x18000bef0`
- `0x18000bf30`

## callees

- `0x180002061`

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
0x18000302c  jmp     free_0
```
