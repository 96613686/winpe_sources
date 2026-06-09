# operator delete(void *)

- ea: `0x180002976`
- end: `0x18000297c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001c20`
- `0x180001c50`
- `0x180001c90`
- `0x180001cc8`
- `0x180001dc8`
- `0x1800029c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002976`

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
0x180002976  jmp     cs:__imp_??3@YAXPEAX@Z
```
