# memmove

- ea: `0x1800092dc`
- end: `0x1800092e2`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005cf0`
- `0x18000f9d0`
- `0x1800126ec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1800092dc`

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
0x1800092dc  jmp     cs:__imp_memmove
```
