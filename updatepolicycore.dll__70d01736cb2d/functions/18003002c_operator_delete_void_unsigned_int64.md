# operator delete(void *,unsigned __int64)

- ea: `0x18003002c`
- end: `0x180030031`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `104`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005150`
- `0x180005310`
- `0x180005380`
- `0x1800054f0`
- `0x1800061bc`
- `0x180006290`
- `0x180006730`
- `0x18000676c`
- `0x180006918`
- `0x18000693c`
- `0x180008e80`
- `0x18000a200`
- `0x18000e588`
- `0x18000e620`
- `0x18000e6a0`
- `0x18000e710`
- `0x18000e8cc`
- `0x18000ea40`
- `0x18000ec2c`
- `0x18000ed90`
- `0x18000edf0`
- `0x18000f018`
- `0x18000f27c`
- `0x18000f688`
- `0x18000f6ac`
- `0x18000f72c`
- `0x18000f7c8`
- `0x18000fdb0`
- `0x180010150`
- `0x180010260`
- `0x1800122f0`
- `0x180014ba0`
- `0x180014bd0`
- `0x180014dbc`
- `0x180014e20`
- `0x180014f24`
- `0x180016eb0`
- `0x180017b30`
- `0x180017bd0`
- `0x180017c70`
- `0x180018020`
- `0x1800183d0`
- `0x1800185b8`
- `0x1800185e8`
- `0x180018690`
- `0x1800192a4`
- `0x180019770`
- `0x1800197a4`
- `0x180019ec0`
- `0x18001a24c`

## callees

- `0x18002ffb0`

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
0x18003002c  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
