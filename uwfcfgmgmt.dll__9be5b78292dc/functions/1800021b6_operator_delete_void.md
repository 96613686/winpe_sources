# operator delete(void *)

- ea: `0x1800021b6`
- end: `0x1800021bc`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void __fastcall(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800014c0`
- `0x1800014f0`
- `0x180001530`
- `0x180001568`
- `0x180001668`
- `0x1800026a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800021b6`

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
0x1800021b6  jmp     cs:__imp_??3@YAXPEAX@Z
```
