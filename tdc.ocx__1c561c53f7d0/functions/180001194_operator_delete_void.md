# operator delete(void *)

- ea: `0x180001194`
- end: `0x180001199`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `23`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800011a0`
- `0x180002bc0`
- `0x180002c20`
- `0x180002c80`
- `0x180002d00`
- `0x180009530`
- `0x18000af64`
- `0x18000b104`
- `0x18000b154`
- `0x18000b370`
- `0x18000b6f8`
- `0x18000bf3c`
- `0x18000c1e0`
- `0x18000c30c`
- `0x18000cf10`
- `0x18000d9b0`
- `0x18000e790`
- `0x18000f130`
- `0x18000f170`
- `0x18000f1b0`
- `0x180010d30`
- `0x180012420`
- `0x180012bac`

## callees

- `0x1800016de`

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
0x180001194  jmp     free_0
```
