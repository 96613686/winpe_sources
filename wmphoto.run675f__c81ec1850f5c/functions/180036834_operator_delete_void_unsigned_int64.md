# operator delete(void *,unsigned __int64)

- ea: `0x180036834`
- end: `0x180036839`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002e1d0`
- `0x18002e2c0`
- `0x18002e2fc`
- `0x18002e400`
- `0x18002e43c`
- `0x18002e570`
- `0x180034940`
- `0x1800355a0`
- `0x180038370`
- `0x1800383b0`
- `0x1800383f0`
- `0x180038740`
- `0x1800387c0`
- `0x180038e60`
- `0x180039e90`
- `0x18003aa50`
- `0x18003bc00`
- `0x18003bfd0`
- `0x18003c020`
- `0x18003d5a0`
- `0x18003e550`
- `0x1800441af`

## callees

- `0x180037024`

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
0x180036834  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
