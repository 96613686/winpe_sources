# memmove_0

- ea: `0x180001ad2`
- end: `0x180001ad8`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180002380`
- `0x180003d78`
- `0x180005da0`
- `0x180009cb8`
- `0x180009d3c`
- `0x18000a20c`
- `0x18000a44c`

## import_xrefs

- `msvcrt!memmove` at `0x180001ad2`

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
0x180001ad2  jmp     cs:__imp_memmove
```
