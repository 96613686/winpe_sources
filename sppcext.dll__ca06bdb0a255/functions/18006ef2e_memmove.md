# memmove

- ea: `0x18006ef2e`
- end: `0x18006ef34`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x1800055ec`
- `0x18000693c`
- `0x1800161ac`
- `0x18001627c`
- `0x180033bb0`
- `0x180039650`
- `0x18003973c`
- `0x18003980c`
- `0x180050ea4`
- `0x180050f98`
- `0x180057ac8`
- `0x180057b84`
- `0x180057c40`

## import_xrefs

- `msvcrt!memmove` at `0x18006ef2e`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x18006ef2e  jmp     cs:__imp_memmove
```
