# operator delete(void *)

- ea: `0x180024a0d`
- end: `0x180024a13`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180025430`
- `0x180025460`
- `0x1800254a0`
- `0x1800254d8`
- `0x1800255d8`
- `0x180025ce0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180024a0d`

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
0x180024a0d  jmp     cs:__imp_??3@YAXPEAX@Z
```
