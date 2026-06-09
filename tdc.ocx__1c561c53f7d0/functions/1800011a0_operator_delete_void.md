# operator delete[](void *)

- ea: `0x1800011a0`
- end: `0x1800011a5`
- name: `??_V@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800026c4`
- `0x180002730`
- `0x180003ef0`
- `0x1800079e0`
- `0x18000b370`
- `0x18000bf3c`
- `0x18000d9b0`
- `0x18000de20`
- `0x18000e078`
- `0x18000f1e8`
- `0x180010bcc`

## callees

- `0x180001194`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete[](void *Block)
{
  operator delete(Block);
}

```

## disassembly

```asm
0x1800011a0  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
