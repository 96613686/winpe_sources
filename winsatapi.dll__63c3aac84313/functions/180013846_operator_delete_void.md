# operator delete(void *)

- ea: `0x180013846`
- end: `0x18001384c`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `5`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180013da0`
- `0x180014760`
- `0x180014b2c`
- `0x180014bac`
- `0x180030bb0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180013846`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
// attributes: thunk
void __fastcall operator delete(void *a1)
{
  __imp_??3@YAXPEAX@Z(a1);
}

```

## disassembly

```asm
0x180013846  jmp     cs:__imp_??3@YAXPEAX@Z
```
