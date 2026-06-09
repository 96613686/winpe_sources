# memmove_0

- ea: `0x18000feb4`
- end: `0x18000feba`
- name: `memmove_0`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800080c8`
- `0x18000a0fc`
- `0x18000a294`
- `0x18000e130`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x18000feb4`

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
0x18000feb4  jmp     cs:__imp_memmove
```
