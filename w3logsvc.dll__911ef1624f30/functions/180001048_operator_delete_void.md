# operator delete(void *)

- ea: `0x180001048`
- end: `0x18000104d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `31`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800022a4`
- `0x1800023a0`
- `0x180005ccc`
- `0x180006c70`
- `0x180007338`
- `0x1800073e8`
- `0x180007984`
- `0x180007cf0`
- `0x180008858`
- `0x180008f90`
- `0x180008fd0`
- `0x180009040`
- `0x18000921c`
- `0x180009604`
- `0x180009d10`
- `0x18000aca8`
- `0x18000b010`
- `0x18000b050`
- `0x18000b090`
- `0x18000b0c0`
- `0x18000b100`
- `0x18000c944`
- `0x18000cb30`
- `0x18000d180`
- `0x18000d780`
- `0x18000e490`
- `0x18000ed06`
- `0x18000f00a`
- `0x18000f058`
- `0x18000f07e`
- `0x18000f0ca`

## callees

- `0x180001549`

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
