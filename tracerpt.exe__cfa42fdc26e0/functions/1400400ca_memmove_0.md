# memmove_0

- ea: `0x1400400ca`
- end: `0x1400400d0`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140038850`
- `0x14003e3a0`

## import_xrefs

- `msvcrt!memmove` at `0x1400400ca`

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
0x1400400ca  jmp     cs:__imp_memmove
```
