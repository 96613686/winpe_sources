# operator delete(void *,unsigned __int64)

- ea: `0x180036264`
- end: `0x180036269`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `22`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18002deb0`
- `0x18002dfa0`
- `0x18002dfdc`
- `0x18002e0e0`
- `0x18002e11c`
- `0x18002e240`
- `0x180034390`
- `0x180034fd0`
- `0x180037d40`
- `0x180037d80`
- `0x180037dc0`
- `0x180038100`
- `0x180038180`
- `0x180038800`
- `0x180039770`
- `0x18003a300`
- `0x18003b430`
- `0x18003b6e0`
- `0x18003b730`
- `0x18003cd70`
- `0x18003ddd0`
- `0x18004399f`

## callees

- `0x180036560`

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
0x180036264  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
