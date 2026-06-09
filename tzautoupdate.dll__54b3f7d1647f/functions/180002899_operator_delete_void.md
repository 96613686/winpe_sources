# operator delete(void *)

- ea: `0x180002899`
- end: `0x18000289f`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180002180`
- `0x1800021c0`
- `0x1800028f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002899`

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
0x180002899  jmp     cs:__imp_??3@YAXPEAX@Z
```
