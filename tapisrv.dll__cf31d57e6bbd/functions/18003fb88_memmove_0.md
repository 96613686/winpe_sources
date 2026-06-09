# memmove_0

- ea: `0x18003fb88`
- end: `0x18003fb8e`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180014710`
- `0x18002b450`
- `0x18002ff78`
- `0x180032fc8`
- `0x18003a3d0`
- `0x18003ce2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18003fb88`

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
0x18003fb88  jmp     cs:__imp_memmove
```
