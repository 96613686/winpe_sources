# operator delete[](void *)

- ea: `0x180001cd4`
- end: `0x180001cd9`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __fastcall(void *)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002218`
- `0x180002234`
- `0x1800028d0`
- `0x1800034cc`
- `0x180003b98`
- `0x180003e10`
- `0x180004420`
- `0x18000462c`
- `0x180004e1c`
- `0x1800052d0`
- `0x180005488`
- `0x180005a9c`
- `0x180005d24`

## callees

- `0x180001ce0`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x180001cd4  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
