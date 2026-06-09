# operator delete(void *,unsigned __int64)

- ea: `0x140001b90`
- end: `0x140001b95`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `55`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1400035d0`
- `0x140003640`
- `0x1400036a0`
- `0x140003de0`
- `0x1400056d0`
- `0x140006680`
- `0x140007548`
- `0x14000805c`
- `0x14000852c`
- `0x1400091a0`
- `0x1400091e0`
- `0x14000c680`
- `0x14000d264`
- `0x14000d420`
- `0x14000d9e0`
- `0x14000e860`
- `0x14000ec28`
- `0x14000ef30`
- `0x14000f110`
- `0x14000f150`
- `0x14000f1e4`
- `0x14000fae0`
- `0x140010664`
- `0x1400107a0`
- `0x1400108dc`
- `0x1400109f0`
- `0x140010a30`
- `0x140010aa0`
- `0x140010ae0`
- `0x140010b20`
- `0x140010b60`
- `0x140010ba0`
- `0x140010be0`
- `0x140010c20`
- `0x140010c60`
- `0x140010cac`
- `0x140010d98`
- `0x140010e70`
- `0x140011200`
- `0x1400114c8`
- `0x140011814`
- `0x140011bb0`
- `0x140012254`
- `0x1400125d0`
- `0x140012a20`
- `0x140012a60`
- `0x140012d4c`
- `0x140013340`
- `0x140013380`
- `0x1400133c0`

## callees

- `0x140001b44`

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
0x140001b90  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
