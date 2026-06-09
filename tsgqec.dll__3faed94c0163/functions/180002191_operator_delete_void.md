# operator delete(void *)

- ea: `0x180002191`
- end: `0x180002197`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001470`
- `0x1800014a0`
- `0x1800014e0`
- `0x180001518`
- `0x180001618`
- `0x180002300`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002191`

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
0x180002191  jmp     cs:__imp_??3@YAXPEAX@Z
```
