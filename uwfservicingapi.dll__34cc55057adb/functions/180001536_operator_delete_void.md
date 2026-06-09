# operator delete(void *)

- ea: `0x180001536`
- end: `0x18000153c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `13`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001b70`
- `0x180001ba0`
- `0x180001be0`
- `0x180001c18`
- `0x180001d18`
- `0x180002510`
- `0x1800031c0`
- `0x180003970`
- `0x18000399c`
- `0x180003d68`
- `0x180004008`
- `0x18000422c`
- `0x1800043f4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001536`

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
0x180001536  jmp     cs:__imp_??3@YAXPEAX@Z
```
