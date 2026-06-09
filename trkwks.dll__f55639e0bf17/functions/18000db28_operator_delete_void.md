# operator delete(void *)

- ea: `0x18000db28`
- end: `0x18000db2d`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `18`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001500`
- `0x1800016b8`
- `0x180001b64`
- `0x180002c90`
- `0x1800048e0`
- `0x1800090c8`
- `0x18000a618`
- `0x18000b060`
- `0x18000baac`
- `0x18000d1fc`
- `0x18000d228`
- `0x18000d3f4`
- `0x18000d864`
- `0x18000ee9c`
- `0x18000f600`
- `0x18000f640`
- `0x18000fd48`
- `0x180010638`

## callees

- `0x18000e35c`

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
0x18000db28  jmp     free_0
```
