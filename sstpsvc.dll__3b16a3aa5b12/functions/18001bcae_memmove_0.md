# memmove_0

- ea: `0x18001bcae`
- end: `0x18001bcb4`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800125bc`
- `0x180012d30`
- `0x18001308c`

## import_xrefs

- `msvcrt!memmove` at `0x18001bcae`

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
0x18001bcae  jmp     cs:__imp_memmove
```
