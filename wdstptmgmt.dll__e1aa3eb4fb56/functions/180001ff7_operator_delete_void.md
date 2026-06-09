# operator delete(void *)

- ea: `0x180001ff7`
- end: `0x180001ffd`
- name: `??3@YAXPEAX@Z_0`
- size: `6`
- prototype: `void(void *)`
- caller_count: `6`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800012f0`
- `0x180001320`
- `0x180001360`
- `0x180001398`
- `0x180001498`
- `0x1800021d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001ff7`

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
0x180001ff7  jmp     cs:__imp_??3@YAXPEAX@Z
```
