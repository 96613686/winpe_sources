# operator delete(void *)

- ea: `0x1800015ad`
- end: `0x1800015b3`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180001c20`
- `0x180001c50`
- `0x180001c90`
- `0x180001cc8`
- `0x180001dc8`
- `0x1800024c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800015ad`

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
0x1800015ad  jmp     cs:__imp_??3@YAXPEAX@Z
```
