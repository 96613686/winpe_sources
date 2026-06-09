# operator delete(void *,unsigned __int64)

- ea: `0x180005278`
- end: `0x18000527d`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `11`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002290`
- `0x1800077c0`
- `0x180007800`
- `0x180007840`
- `0x180007880`
- `0x1800126a0`
- `0x1800133bc`
- `0x180013acc`
- `0x180015970`
- `0x18001643c`
- `0x1800168a8`

## callees

- `0x180005284`

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
0x180005278  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
