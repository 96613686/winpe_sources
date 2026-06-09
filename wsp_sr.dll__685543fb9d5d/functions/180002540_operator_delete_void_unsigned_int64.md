# operator delete(void *,unsigned __int64)

- ea: `0x180002540`
- end: `0x180002545`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *, unsigned __int64)`
- caller_count: `31`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004ce0`
- `0x18000573c`
- `0x180005b10`
- `0x180005b60`
- `0x180008ec0`
- `0x180008efc`
- `0x180008f40`
- `0x180011a40`
- `0x180011a80`
- `0x180017a40`
- `0x180017a80`
- `0x180017ac0`
- `0x180017b00`
- `0x180017b40`
- `0x180017b80`
- `0x180020280`
- `0x180024490`
- `0x180026160`
- `0x180028318`
- `0x180028350`
- `0x180028390`
- `0x1800283d0`
- `0x180028410`
- `0x180028940`
- `0x180028990`
- `0x180028af0`
- `0x1800291d0`
- `0x18002b242`
- `0x18002bbc6`
- `0x18002c347`
- `0x18002c6d5`

## callees

- `0x180002954`

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
0x180002540  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
