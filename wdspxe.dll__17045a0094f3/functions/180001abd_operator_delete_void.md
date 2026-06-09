# operator delete(void *)

- ea: `0x180001abd`
- end: `0x180001ac3`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180002100`
- `0x180002130`
- `0x180002170`
- `0x1800021a8`
- `0x1800022a8`
- `0x1800029a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001abd`

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
0x180001abd  jmp     cs:__imp_??3@YAXPEAX@Z
```
