# operator delete(void *,unsigned __int64)

- ea: `0x140001260`
- end: `0x140001265`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `9`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140002be0`
- `0x140003a20`
- `0x140003a60`
- `0x140003ac0`
- `0x140003b00`
- `0x140003b30`
- `0x140003b60`
- `0x140005b90`
- `0x14000678c`

## callees

- `0x14000126c`

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
0x140001260  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
