# memmove_0

- ea: `0x18002a55a`
- end: `0x18002a560`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002738c`
- `0x1800273f4`

## import_xrefs

- `msvcrt!memmove` at `0x18002a55a`

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
0x18002a55a  jmp     cs:__imp_memmove
```
