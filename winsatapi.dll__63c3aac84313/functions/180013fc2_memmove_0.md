# memmove_0

- ea: `0x180013fc2`
- end: `0x180013fc8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180004b10`
- `0x18000eb34`
- `0x180029780`

## import_xrefs

- `msvcrt!memmove` at `0x180013fc2`

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
0x180013fc2  jmp     cs:__imp_memmove
```
