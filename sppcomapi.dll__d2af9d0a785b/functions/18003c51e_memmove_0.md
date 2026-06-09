# memmove_0

- ea: `0x18003c51e`
- end: `0x18003c524`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000405c`
- `0x18001ca2c`
- `0x18001cc48`
- `0x18001e9c4`
- `0x18001eb40`
- `0x180037118`
- `0x18003bd80`

## import_xrefs

- `msvcrt!memmove` at `0x18003c51e`

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
0x18003c51e  jmp     cs:__imp_memmove
```
