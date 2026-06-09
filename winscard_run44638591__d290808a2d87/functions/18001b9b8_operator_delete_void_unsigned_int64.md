# operator delete(void *,unsigned __int64)

- ea: `0x18001b9b8`
- end: `0x18001b9bd`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `77`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001ab0`
- `0x180002220`
- `0x180002a30`
- `0x180002d40`
- `0x180003790`
- `0x180003ee0`
- `0x180003fc0`
- `0x1800040d0`
- `0x1800046a0`
- `0x180004ca0`
- `0x1800055c0`
- `0x180005b00`
- `0x180005de0`
- `0x180007f40`
- `0x180008f70`
- `0x180009480`
- `0x180009c10`
- `0x18000a290`
- `0x18000aa80`
- `0x18000bd60`
- `0x18000cae0`
- `0x18000cd90`
- `0x18000d320`
- `0x18000d640`
- `0x18000dbf0`
- `0x18000e090`
- `0x18000e110`
- `0x18000e3d0`
- `0x18000e980`
- `0x18000fb40`
- `0x18000fd94`
- `0x18000ff40`
- `0x180010400`
- `0x180011880`
- `0x180011b70`
- `0x180012000`
- `0x180012480`
- `0x180012650`
- `0x180012d80`
- `0x180012f80`
- `0x1800131dc`
- `0x180013b20`
- `0x180014220`
- `0x180014260`
- `0x180014440`
- `0x180014720`
- `0x180014760`
- `0x180014f50`
- `0x1800158b0`
- `0x1800158f0`

## callees

- `0x18001ba10`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x18001b9b8  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
