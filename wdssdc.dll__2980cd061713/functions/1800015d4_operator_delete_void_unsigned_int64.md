# operator delete(void *,unsigned __int64)

- ea: `0x1800015d4`
- end: `0x1800015d9`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `42`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800027e0`
- `0x180002860`
- `0x1800028e0`
- `0x18000291c`
- `0x180003384`
- `0x180003680`
- `0x180004f40`
- `0x1800057e8`
- `0x1800058c0`
- `0x18000592c`
- `0x180005c20`
- `0x180005dac`
- `0x180005fe8`
- `0x180006a60`
- `0x180006f00`
- `0x180007214`
- `0x1800079d4`
- `0x180007ab0`
- `0x180008cfc`
- `0x180008f70`
- `0x18000906c`
- `0x180009194`
- `0x180009278`
- `0x180009300`
- `0x180009554`
- `0x180009770`
- `0x1800098dc`
- `0x180009990`
- `0x180009ba8`
- `0x180009e70`
- `0x18000a980`
- `0x18000ac28`
- `0x18000ae80`
- `0x18000b6d4`
- `0x18000b960`
- `0x18000bc94`
- `0x18000be44`
- `0x18000bec0`
- `0x18000bf70`
- `0x18000c344`
- `0x18000c3c4`
- `0x18000c7f8`

## callees

- `0x180001594`

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
0x1800015d4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
