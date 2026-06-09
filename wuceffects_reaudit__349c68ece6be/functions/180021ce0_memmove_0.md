# memmove_0

- ea: `0x180021ce0`
- end: `0x180021ce6`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a60`
- `0x180002e78`
- `0x180004df4`
- `0x180004ffc`
- `0x180007bc0`
- `0x18000ae70`
- `0x18000bfb0`
- `0x18000d004`
- `0x18000d0d4`
- `0x18000e1b4`
- `0x18000fba4`
- `0x18001a8b0`
- `0x18002093c`
- `0x180026144`
- `0x1800261c0`
- `0x180028ddc`
- `0x180029ab0`
- `0x18002b188`
- `0x18002c42e`
- `0x18002c4ad`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x180021ce0`

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
0x180021ce0  jmp     cs:__imp_memmove
```
