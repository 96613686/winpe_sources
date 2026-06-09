# memmove_0

- ea: `0x18001b3e2`
- end: `0x18001b3e8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002300`
- `0x1800104a8`
- `0x180010548`
- `0x180010958`

## import_xrefs

- `msvcrt!memmove` at `0x18001b3e2`

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
0x18001b3e2  jmp     cs:__imp_memmove
```
