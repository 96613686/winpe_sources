# memmove_0

- ea: `0x18000f9ce`
- end: `0x18000f9d4`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180003790`
- `0x180003fd0`
- `0x1800062a0`

## import_xrefs

- `msvcrt!memmove` at `0x18000f9ce`

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
0x18000f9ce  jmp     cs:__imp_memmove
```
