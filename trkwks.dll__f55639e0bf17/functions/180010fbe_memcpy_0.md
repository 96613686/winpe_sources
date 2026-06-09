# memcpy_0

- ea: `0x180010fbe`
- end: `0x180010fc4`
- name: `memcpy_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800047b0`
- `0x180006850`
- `0x1800090c8`
- `0x18000c55c`
- `0x18000cf58`
- `0x18000fd48`

## import_xrefs

- `msvcrt!memcpy` at `0x180010fbe`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy_0(void *a1, const void *Src, size_t Size)
{
  return memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x180010fbe  jmp     cs:__imp_memcpy
```
