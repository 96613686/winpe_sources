# operator delete(void *)

- ea: `0x180003a86`
- end: `0x180003a8c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180002d90`
- `0x180002dc0`
- `0x180002e00`
- `0x180002e38`
- `0x180002f38`
- `0x180003f80`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003a86`

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
0x180003a86  jmp     cs:__imp_??3@YAXPEAX@Z
```
