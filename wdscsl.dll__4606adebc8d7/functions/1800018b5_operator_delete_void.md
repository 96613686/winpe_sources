# operator delete(void *)

- ea: `0x1800018b5`
- end: `0x1800018bb`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001e30`
- `0x180001e60`
- `0x180001ea0`
- `0x180001ed8`
- `0x180001fd8`
- `0x1800026d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800018b5`

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
0x1800018b5  jmp     cs:__imp_??3@YAXPEAX@Z
```
