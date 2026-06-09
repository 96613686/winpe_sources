# operator delete(void *)

- ea: `0x1800015c7`
- end: `0x1800015cd`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001d00`
- `0x180001d30`
- `0x180001d70`
- `0x180001da8`
- `0x180001ea8`
- `0x180002540`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800015c7`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  __imp_??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x1800015c7  jmp     cs:__imp_??3@YAXPEAX@Z
```
