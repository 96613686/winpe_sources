# operator delete(void *)

- ea: `0x180009792`
- end: `0x180009798`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `2`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180009030`
- `0x1800097f0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009792`

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
0x180009792  jmp     cs:__imp_??3@YAXPEAX@Z
```
