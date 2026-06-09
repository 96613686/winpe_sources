# memmove_0

- ea: `0x18001b76e`
- end: `0x18001b774`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e378`
- `0x180010fe0`
- `0x180014f38`
- `0x180015478`

## import_xrefs

- `msvcrt!memmove` at `0x18001b76e`

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
0x18001b76e  jmp     cs:__imp_memmove
```
