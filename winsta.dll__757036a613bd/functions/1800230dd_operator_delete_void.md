# operator delete(void *)

- ea: `0x1800230dd`
- end: `0x1800230e3`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180023ae0`
- `0x180023b10`
- `0x180023b50`
- `0x180023b88`
- `0x180023c88`
- `0x180024390`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800230dd`

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
0x1800230dd  jmp     cs:__imp_??3@YAXPEAX@Z
```
