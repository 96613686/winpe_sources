# operator delete(void *)

- ea: `0x1400088d6`
- end: `0x1400088dc`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x140008050`
- `0x140008080`
- `0x1400080c0`
- `0x1400080f8`
- `0x1400081f8`
- `0x1400088a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400088d6`

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
0x1400088d6  jmp     cs:__imp_??3@YAXPEAX@Z
```
