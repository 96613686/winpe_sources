# memmove_0

- ea: `0x18001d32e`
- end: `0x18001d334`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180008840`

## import_xrefs

- `msvcrt!memmove` at `0x18001d32e`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove_0(void *a1, const void *Src, size_t Size)
{
  return memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18001d32e  jmp     cs:__imp_memmove
```
