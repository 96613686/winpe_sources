# operator delete(void *)

- ea: `0x180001926`
- end: `0x18000192c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001300`
- `0x180001340`
- `0x180001e40`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001926`

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
0x180001926  jmp     cs:__imp_??3@YAXPEAX@Z
```
