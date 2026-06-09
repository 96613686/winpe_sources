# memmove_0

- ea: `0x18002a07c`
- end: `0x18002a082`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b478`
- `0x1800102b4`
- `0x180013d60`
- `0x18001cf04`
- `0x18001fd4c`
- `0x18001feb0`
- `0x180020030`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18002a07c`

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
0x18002a07c  jmp     cs:__imp_memmove
```
