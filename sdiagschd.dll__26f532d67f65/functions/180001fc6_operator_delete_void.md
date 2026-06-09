# operator delete(void *)

- ea: `0x180001fc6`
- end: `0x180001fcc`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800012b0`
- `0x1800012e0`
- `0x180001320`
- `0x180001358`
- `0x180001458`
- `0x1800020d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001fc6`

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
0x180001fc6  jmp     cs:__imp_??3@YAXPEAX@Z
```
